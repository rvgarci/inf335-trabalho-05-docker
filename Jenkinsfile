pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    bat """
                    docker build -t inf335-trabalho-05 .
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    bat """
                    docker run --rm inf335-trabalho-05
                    """
                }
            }
        }
    }
}
