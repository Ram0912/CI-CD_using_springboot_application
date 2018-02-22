pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''mvn clean install package
docker rmi -f etms-rest
docker build -t etms-rest

'''
      }
    }
  }
}