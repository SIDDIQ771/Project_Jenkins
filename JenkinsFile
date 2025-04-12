pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/SIDDIQ771/Project_Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                sh './build.sh'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './run-tests.sh'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh './deploy.sh'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed. Please check logs.'
        }
    }
}
