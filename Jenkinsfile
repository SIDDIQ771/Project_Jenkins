pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SIDDIQ771/Project_Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy to Production') {
      steps {
        input message: 'Deploy to production?', ok: 'Yes, deploy'
        sh './deploy-production.sh' // Use a deployment script
      }

        stage('Deployed Changes') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed. Please check logs.'
        }
    }
}
