pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''mvn clean install package


'''
      }
    }
    stage('error') {
      steps {
        sh 'docker build -t sample-rest .'
      }
    }
  }
}