pipeline {
    agent any

    stages {
        stage('Pull SCM') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Adarshmetgud/Amazon-Jenkins.git'
            }
        }

        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }

    post {
        success {
            emailext(
                to: 'adarshmetgud059@gmail.com',
                subject: 'Build SUCCESS',
                body: 'Amazon project build completed successfully!'
            )
        }

        failure {
            emailext(
                to: 'adarshmetgud059@gmail.com',
                subject: 'Build FAILURE',
                body: 'Amazon project build failed. Check Jenkins Console Output.'
            )
        }
    }
}
