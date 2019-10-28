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
      when {
        branch 'master'
      }
      steps {
        sh './gradlew test'
      }
    }
  }
  post {
    always {
      junit 'build/**/*.xml'
    }
  }
}
