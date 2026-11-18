pipeline {
    agent { label 'Node1' }

    stages {
        stage('Compile') {
            steps {
                sh '#!/bin/bash\nmvn compile'
            }
        }

        stage('Build') {
            steps {
                sh '#!/bin/bash\nmvn clean install'
            }
        }
    }

    post {
        success {
            emailext(
                to: 'shubhammarata.reports@gmail.com',
                subject: "Jenkins Pipeline - ${env.JOB_NAME} - SUCCESS",
                body: "Your Jenkins Pipeline is successful"
            )
        }
        failure {
            emailext(
                to: 'shubhammarata.reports@gmail.com',
                subject: "Jenkins Pipeline - ${env.JOB_NAME} - FAILURE",
                body: "Your Jenkins Pipeline has failed"
            )
        }
    }
}
