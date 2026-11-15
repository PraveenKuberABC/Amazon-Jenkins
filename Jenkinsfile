pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Checking out code..."
            }
        }

        stage('Build') {
            steps {
                echo "Building application..."
            }
        }

        stage('Test') {
            steps {
                echo "Executing tests..."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
            }
        }
    }

    post {
        success {
            echo "Pipeline executed successfully"
        }

        failure {
            echo "Pipeline execution failed"
        }
    }
}
