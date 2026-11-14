pipeline {
    agent any
    stages {
        stage('clean') {
            steps {
                echo "Building branch: ${env.GIT_BRANCH}"
                sh 'mvn clean'
            }
        }
        stage('validate') {
            steps {
                sh 'mvn validate'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
    post {
        success {
            echo 'Build success from Jenkinsfile'
        }
        failure {
            echo 'Failure in the build'
        }
    }
}
