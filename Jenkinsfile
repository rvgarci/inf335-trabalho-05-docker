pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Exemplo de construção de uma imagem Docker
                    docker.build('nome-da-imagem:tag') 
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Exemplo de execução de um contêiner Docker
                    docker.image('nome-da-imagem:tag').run() 
                }
            }
        }
    }
}
