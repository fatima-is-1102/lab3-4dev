pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat 'docker --version && docker build -t newimg .'
      }
    }

    stage('run') {
      steps {
        bat 'docker rm -f newlab >nul 2>&1 & docker run -d -p 8081:80 --name newlab newimg'
      }
    }

    stage('verify') {
      steps {
        bat 'docker ps'
      }
    }

  }
}