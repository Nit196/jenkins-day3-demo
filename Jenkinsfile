
pipeline {

    agent any

    environment {
        APP_NAME = 'banking-app'
        ENVIRONMENT = 'DEV'
    }

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
        disableConcurrentBuilds()
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                sh 'pwd'
                sh 'ls -la'
                sh 'git log -1 --oneline'
            }
        }

        stage('Build') {
            steps {
                echo "Building ${APP_NAME}"
                echo "Target environment: ${ENVIRONMENT}"
            }
        }

        stage('Test') {
            steps {
                echo 'Executing unit tests'
                echo 'All tests passed'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging application'
                echo 'JAR generation simulated'
            }
        }
    }

    post {

        always {
            echo 'Pipeline execution completed'
        }

        success {
            echo 'Pipeline completed successfully'
        }

        failure {
            echo 'Pipeline execution failed'
        }
    }
}
