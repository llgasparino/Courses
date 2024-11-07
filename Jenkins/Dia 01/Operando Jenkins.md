# Projeto que vamos utilizar
> guia-pratico-jenkins
#### Nota: Dentro do Fedora
> Desktop/Projetos/Jenkins/guia-pratico-jenkins
### Acessar ip da maquina na porta 8080
> Novo item > Pipeline > Repositorio git
### Estrutura básica jenkins
    pipeline {
        agent any
        
        stages {
            stage('Build Docker Image'){
                steps{
                    echo 'Executando o comando Docker Build'
                }
            }
            stage('Push Docker Image'){
                steps{
                    echo 'Executando o comando Docker Push'
                }
            }
            stage('Deploy no k8s'){
                steps{
                    echo 'Executando o comando kubectl apply'
                }
            }
        }
    }
### Jenkinsfile usando plugin
    pipeline {
        agent any
        
        stages {
            stage('Build Docker Image'){
                steps{
                    script {
                        dockerapp = docker.build("llgasparino/guia-jenkins:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                    }
                }
            }
            stage('Push Docker Image'){
                steps{
                    script {
                        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                            dockerapp.push('latest')
                            dockerapp.push("${env.BUILD_ID}")
                        } 
                    }
                }
            }
            stage('Deploy no k8s'){
                steps{
                    echo 'Executando o comando kubectl apply'
                }
            }
        }
    }