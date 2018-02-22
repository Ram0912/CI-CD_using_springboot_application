pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''mvn clean install package


'''
      }
    }
    stage('Image building ') {
      steps {
        sh 'docker build -t sample-rest .'
      }
    }
    stage('') {
      steps {
        slackSend(message: 'build of sample demo is ready', channel: '#sample', color: 'green', failOnError: true)
      }
    }
  }
}