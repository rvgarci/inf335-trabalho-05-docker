pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                script {
                    bat """
                    docker build -t inf335-trabalho-05 .
                    """
                }
            }
        }
        stage('run') {
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
