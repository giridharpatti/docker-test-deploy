pipeline {
  agent {
    label 'slave3'
  }
  environment{
     CODEDIR='/var/lib/jenkins/workspace/docker-deploy/dockertest-deploy'    
    }
  stages {
     stage('clone repo') {
       steps {
        sh "rm -rf *"
        sh "git clone -b develop git@github.com:giridharpatti/dockertest.git"
       }
     }
    stage('Build') {
      steps {
        dir("${env.CODEDIR}") {
        echo 'Building docker-compose'
        sh '''
        docker-compose up -d
        }
      }
    }
  }
}
