pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''DOCKER_HOST=unix:///var/run/docker.sock mvn clean package docker:build

'''
      }
    }
  }
}