pipeline {
  agent any

  environment {
      MESSAGE_BEGIN = 'Hello, world'
      MESSAGE_END = 'Done...'
  }

  stages {
    stage('Start') {
      steps {
        echo "${MESSAGE_BEGIN}"
      }
    }
    stage('Test') {
      when {
        branch 'develop'
      }
      steps {
        sh './gradlew test'
      }
    }
    stage('Report') {
      when {
        branch 'develop'
      }
      steps {
        junit 'build/**/*.xml'
      }
    }
  }
  post {
    always {
      echo "${MESSAGE_END}"
    }
  }
}
