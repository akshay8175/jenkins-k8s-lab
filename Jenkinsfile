
pipeline {

    agent any

    environment {
        IMAGE_NAME = "jenkins-k8s-lab"
        IMAGE_TAG = "${BUILD_NUMBER}"
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                checkout scm
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

                sh '''
                    test -f index.html
                    test -f Dockerfile
                '''
            }
        }

        stage('Docker Build') {
            steps {
                sh """
                    docker build \
                    -t ${IMAGE_NAME}:${IMAGE_TAG} .
                """
            }
        }
    }

    post {

        success {
            echo 'CI pipeline successful!'
        }

        failure {
            echo 'CI pipeline failed!'
        }
    }
}
