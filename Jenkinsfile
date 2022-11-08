pipeline {
  agent {
    label 'slave1'
  }
  stages {
    stage('Deploy') {
      steps {
        script{
        sh '''
        ssh root@10.0.1.37 /bin/bash << EOF
        hostname -I &&
        echo 'Deploying docker-compose in 10.0.1.37' &&
        rm -rf * &&
        git clone -b develop git@github.com:giridharpatti/docker-test-deploy.git &&
        cd docker-test-deploy &&
        sed -i 's/version/$version/g' docker-compose.yml &&
        aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 710222791487.dkr.ecr.ap-south-1.amazonaws.com &&
        docker-compose up -d &&
        exit 0 &&
        << EOF
        '''
        }
      }
    }
  }
}
