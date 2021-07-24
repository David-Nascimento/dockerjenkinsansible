![Captura de tela de 2021-07-23 22-44-19](https://user-images.githubusercontent.com/53004819/126881075-e2024161-33b7-4670-9e93-7061fb3cbf18.png)
# Jenkins CI/CD com Docker, Ansible e AWS

> Projeto criado com proposito didatico pessoal, o projeto visa melhorias na habilidade 
> de entrega continua usando docker e ansible.

### Configuração das Instancia Jenkins 
- Jenkins + Java-8.1
- Docker
- Ansible
- Maven

## Configurando o Jenkins
### Plugins o Jenkins. 
##### Gerenciar Jenkins > Gerenciar Plugins > Disponivel: 
- Ansible  = 1.1
- Maven integration = 3.12
- Docker = 1.2.2

#### Gerenciar Jenkins > Global Tools Configuration
- Java > Nome: jdk3 > Instalar automaticamente > versão 8u201
- Maven > Nome: maven3 > Instalar automaticamente > versão 3.6.1
- Ansible > Nome: ansible > Path: /usr/bin
 
