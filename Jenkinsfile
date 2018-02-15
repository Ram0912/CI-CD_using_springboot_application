pipeline {
  agent any
  stages {
    stage('Initailising') {
      steps {
        bat 'echo initialise'
      }
    }
    stage('maven build') {
      steps {
        bat 'mvn clean install '
      }
    }
  }
}