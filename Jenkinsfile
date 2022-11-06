pipeline {
  agent {
    label 'slave1'
  }
  stages {
    stage('Deploy') {
      steps {
        sh '''
        sudo ssh root@10.0.1.37
        echo 'Deploying docker-compose in 10.0.1.37'
        cd httpd-deploy
        docker-compose up -d
        '''
      }
    }
  }
}
