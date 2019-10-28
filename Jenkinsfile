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
    stage('Report') {
      when {
        branch 'master'
      }
      steps {
        junit 'build/**/*.xml'
      }
    }
  }
  /*
  post {
    always {
      junit 'build/**/*.xml'
    }
  }
  */
}
