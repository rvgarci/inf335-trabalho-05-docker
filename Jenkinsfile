pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                    docker build -t inf335-trabalho-05 .
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh """
                    docker run --rm inf335-trabalho-05
                    """
                }
            }
        }
    }
}
