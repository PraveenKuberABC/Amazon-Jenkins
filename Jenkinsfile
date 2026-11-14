pipeline {
    agent { label 'Node1' }

    stages {
        stage('Pull SCM') {
            steps {
                // Automatically checks out the current branch being built
                checkout scm
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
                to: 'kamran.abc.reports@gmail.com',
                subject: "Jenkins Pipeline - ${env.JOB_NAME} - SUCCESS",
                body: "Your Jenkins Pipeline is successful"
            )
        }

        failure {
            emailext(
                to: 'kamran.abc.reports@gmail.com',
                subject: "Jenkins Pipeline - ${env.JOB_NAME} - FAILURE",
                body: "Your Jenkins Pipeline has failed"
            )
        }
    }
}
