pipeline {
  agent {
    label 'slave1'
  }
  stages {
    stage('Deploy') {
      steps {
        sh '''
        ssh root@10.0.1.37
        echo 'Deploying docker-compose in 10.0.1.37'
        sh "rm -rf *"
        sh "git clone -b develop git@github.com:giridharpatti/docker-test-deploy.git"
        docker-compose up -d
        '''
      }
    }
  }
}
