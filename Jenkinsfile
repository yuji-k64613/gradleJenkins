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
        branch 'develop'
      }
      steps {
        sh './gradlew test'
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
