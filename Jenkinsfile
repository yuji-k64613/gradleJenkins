pipeline {
  agent any

  environment {
      MESSAGE = 'Hello, world'
  }

  stages {
    stage('Start') {
      steps {
        echo "${MESSAGE}"
      }
    }
    stage('Test') {
      steps {
        sh './gradlew test'
      }
    }
  }
}
