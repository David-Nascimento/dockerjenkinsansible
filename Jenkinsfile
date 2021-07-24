pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    environment {
      DOCKER_TAG = getVersion()
    }

    stages{
        stage('SCM') {
            steps{
                git branch: 'main', credentialsId: 'github-key', url: 'https://github.com/David-Nascimento/dockerjenkinsansible'
            }
        }

        stage('Maven Build') {
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Docker Build') {
            steps {
                sh "docker build . -t davidnascimento01/hariapp:${DOCKER_TAG} "
            }
        }
        stage('DockerHub Push'){
            steps{
                withCredentials([string(credentialsId: 'docker-secret', variable: 'dockerHubPwd')]) {
                    sh "docker login -u davidnascimento01 -p ${dockerHubPwd}"
                }

                sh "docker push davidnascimento01/hariapp:${DOCKER_TAG} "
            }
        }
        stage('Docker Deploy'){
            steps{
              ansiblePlaybook credentialsId: 'dev-server', disableHostKeyChecking: true, extras: '-e DOCKER_TAG="${DOCKER_TAG}"', installation: 'ansible', inventory: 'dev.inv', playbook: 'deploy-docker.yml'
            }
        }
    }
}

def getVersion() {
    def commitHash = sh returnStdout: true, script: 'git rev-parse --short HEAD'
    return commitHash
}
