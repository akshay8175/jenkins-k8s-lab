pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application'
                sh 'test -f index.html'
            }
        }
    }

    post {

        success {
            echo 'Pipeline successful!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
