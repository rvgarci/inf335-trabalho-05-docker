pipeline {
    agent {
        label any
    }
    stages {
        stage("build") {
            steps {
                sh """
                docker build -t inf335-trabalho-05 .
                """
            }
        }
    }
}
