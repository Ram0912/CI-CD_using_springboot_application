pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat 'mvn clean && mvn install && mvn package docker:build'
      }
    }
  }
}