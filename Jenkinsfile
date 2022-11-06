pipeline {
  agent {
    label 'slave1'
  }
  stages {
    stage('Deploy') {
      steps {
        sh '''
        ssh root@10.0.1.37 bash
        echo 'Deploying docker-compose in 10.0.1.37'
        cd httpd-deploy
        docker-compose up -d
        '''
      }
    }
  }
}
