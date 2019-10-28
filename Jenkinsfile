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
    stage('Example Deploy') {
      when {
        branch 'master'
      }
      steps {
        echo 'branch is master'
      }
    }
    stage('Test') {
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
