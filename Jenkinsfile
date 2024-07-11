pipeline {
  agent {
    label "linux"
  }
  stages {
    stage("build") {
      steps {
        sh """
        docker build -t OlaMundo .
        """
      }
    }
    stage("run") {
      steps {
        sh """
        docker run --rm OlaMundo
        """
      }
    }
  }
}
