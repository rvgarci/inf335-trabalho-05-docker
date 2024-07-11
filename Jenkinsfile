pipeline {
    agent {
        // Define o agente como sendo Windows
        label 'windows'
    }

    environment {
        // Define variáveis de ambiente para o Docker (ajuste conforme necessário)
        DOCKER_IMAGE = 'meu-aplicativo-java:latest'
        DOCKERFILE_PATH = '.'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    // Constrói a imagem Docker
                    bat "docker build -t ${env.DOCKER_IMAGE} -f ${env.DOCKERFILE_PATH}/Dockerfile ${env.DOCKERFILE_PATH}"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Executa o contêiner Docker para testar a aplicação
                    bat "docker run --rm ${env.DOCKER_IMAGE}"
                }
            }
        }
    }

    post {
        always {
            // Remove a imagem Docker após o Pipeline ser executado (opcional)
            bat "docker rmi ${env.DOCKER_IMAGE} /q"
        }
    }
}
