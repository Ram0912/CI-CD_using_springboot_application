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
    stage('docker env to default') {
      steps {
        bat 'docker-machine env --shell cmd default '
      }
    }
    stage('docker setup') {
      steps {
        bat '@FOR /f "tokens=*" %%i IN (\'docker-machine env --shell cmd default\') DO @%%i'
      }
    }
    stage('docker images build') {
      steps {
        bat 'mvn docker:build'
      }
    }
  }
}