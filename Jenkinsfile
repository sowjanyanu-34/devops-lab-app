pipeline {

  agent any

  environment {
    APP_NAME = 'devops-lab-app'
    VERSION = '1.0.0'
  }

  stages {

    stage('Checkout') {
      steps {
        git branch: 'main',
            url: 'https://github.com/sowjanyanu-34/devops-lab-app.git'
      }
    }

    stage('Build') {
      steps {
        echo 'Building project...'
        sh 'bash build.sh'
      }
    }

  }

  post {
    always {
      echo 'Pipeline completed'
    }
    success {
      echo 'Build SUCCESS'
    }
    failure {
      echo 'Build FAILED'
    }
  }

}
