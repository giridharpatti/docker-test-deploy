pipeline {
  agent {
    label 'slave1'
  }
  stages {
    stage('Deploy') {
      steps {
        ssh root@10.0.1.37
        sh '''
        echo 'Deploying docker-compose in 10.0.1.37'
        sh "rm -rf *"
        sh "git clone -b develop git@github.com:giridharpatti/docker-test-deploy.git"
        cd docker-test-deploy
        docker-compose up -d
        '''
      }
    }
  }
}
