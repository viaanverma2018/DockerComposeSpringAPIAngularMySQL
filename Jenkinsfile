pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo Building'
      }
    }
    stage('Start test image') {
      steps {
        sh 'echo starting'
      }
    }
    stage('E2E Tests') {
      steps {
        sh 'echo e2e'
      }
    }
  }
  post {
    always {
      sh 'echo down'

    }

  }
}