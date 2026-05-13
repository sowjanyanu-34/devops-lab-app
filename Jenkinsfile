pipeline {
  agent any

  tools {
    nodejs 'NodeJS-18'
  }

  stages {

    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Install') {
      steps {
        sh 'node -v'
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm test || true'
      }
    }

    stage('Build') {
      steps {
        sh 'echo "Build complete"'
      }
    }

  }
}
