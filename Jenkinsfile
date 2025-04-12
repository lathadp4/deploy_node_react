pipeline {
  agent any

  environment {
    IMAGE_NAME = "my-app"
  }

  stages {
    stage('Clone Repository') {
      steps {
        git 'https://github.com/lathadp4/deploy_node_react.git'
      }
    }

    stage('Build and Deploy') {
      steps {
        script {
          sh 'docker-compose down'
          sh 'docker-compose build'
          sh 'docker-compose up -d'
        }
      }
    }
  }

  post {
    success {
      echo 'Deployment successful!'
    }
    failure {
      echo 'Deployment failed.'
    }
  }
}
