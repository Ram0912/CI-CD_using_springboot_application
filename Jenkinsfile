pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''export DOCKER_HOST=unix:///var/run/docker.sock
mvn clean package docker:build
'''
      }
    }
  }
}