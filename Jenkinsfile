pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat 'docker --version && docker build -t portfolio .'
      }
    }

    stage('run') {
      steps {
        bat ' docker rm -f portfolio-container >nul 2>&1 & docker run -d -p 8081:80 --name portfolio-container portfolio'
      }
    }

    stage('verify') {
      steps {
        bat 'docker ps'
      }
    }

  }
}