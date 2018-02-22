pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''mvn clean install package


'''
        git(url: 'https://github.com/Ram0912/CI-CD_using_springboot_application.git', branch: 'ubuntu-blue', changelog: true, poll: true)
      }
    }
    stage('Image building ') {
      steps {
        sh '''docker rmi -f sample-rest
docker build -t sample-rest .'''
      }
    }
    stage('Slack message') {
      parallel {
        stage('Slack message') {
          steps {
            slackSend(message: 'build of sample demo is ready', channel: '#sample', color: 'green', failOnError: true)
          }
        }
        stage('Local resgistry push') {
          steps {
            sh '''docker tag sample-rest localhost:5000/sample-rest
docker push localhost:5000/sample-rest
'''
          }
        }
      }
    }
    stage('Completed') {
      steps {
        echo 'Docker rigistry push done'
      }
    }
  }
}