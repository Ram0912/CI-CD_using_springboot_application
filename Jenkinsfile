pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''mvn clean install package
sudo docker rmi -f etms-rest
sudo docker build -t etms-rest

'''
      }
    }
  }
}