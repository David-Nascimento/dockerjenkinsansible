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
 