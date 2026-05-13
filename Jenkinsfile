pipeline {

  agent any

  environment {
    APP_NAME = 'devops-lab-app'
    APP_PORT = '3000'
  }

  stages {

    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm test || true'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t devops-lab-app .'
      }
    }

    stage('Run Container') {
      steps {
        sh '''
          docker stop app || true
          docker rm app || true
          docker run -d -p 3000:3000 --name app devops-lab-app
        '''
      }
    }

  }
}
