pipeline {
    agent any

    environment {
        // Defina as variáveis de ambiente para o Docker
        DOCKER_IMAGE = 'inf335-trabalho-05' // Nome da imagem Docker
        DOCKERFILE_PATH = '.' // Caminho para o Dockerfile, se estiver na raiz do projeto
    }

    stages {
        stage('Build') {
            steps {
                script {
                    // Constrói a imagem Docker
                    docker.build("${DOCKER_IMAGE}:${BUILD_NUMBER}", "-t ${DOCKER_IMAGE} -f ${DOCKERFILE_PATH}/Dockerfile ${DOCKERFILE_PATH}")
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Executa o contêiner Docker para testar a aplicação
                    docker.image("${DOCKER_IMAGE}:${BUILD_NUMBER}").run("--rm")
                }
            }
        }
    }

    post {
        always {
            // Remove a imagem Docker após o Pipeline ser executado (opcional)
            script {
                docker.image("${DOCKER_IMAGE}:${BUILD_NUMBER}").remove(force: true)
            }
        }
    }
}
