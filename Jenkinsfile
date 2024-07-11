pipeline {
  agent {
    label "windows"
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
