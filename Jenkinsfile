pipeline {
    agent any

    stages {
        stage('Maven Test') {
            steps {
                sh 'mvn clean test'
            }
        }

        stage('Maven Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully'
        }

        failure {
            echo 'Pipeline got failed'
        }
    }
}
