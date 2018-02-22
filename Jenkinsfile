pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''mvn clean install package


'''
      }
    }
    stage('') {
      steps {
        sh 'docker build -t sample-rest'
      }
    }
  }
}