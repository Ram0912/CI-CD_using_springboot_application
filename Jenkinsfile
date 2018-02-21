pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''mvn clean package docker:build
'''
      }
    }
  }
}