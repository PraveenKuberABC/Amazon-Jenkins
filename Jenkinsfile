pipeline {
    agent any

    environment {
        GIT_BRANCH = 'demo'
        GIT_URL = 'https://github.com/sapsoni-hue/Amazon-Jenkins.git'
    }

    stages {

        stage('Clone Project') {
            steps {
                echo 'Cloning Amazon-Jenkins Repository'

                git branch: "${env.GIT_BRANCH}",
                    url: "${env.GIT_URL}"
            }
        }

        stage('Verify Workspace') {
            steps {
                echo "Current Branch: ${env.GIT_BRANCH}"
                sh 'pwd'
                sh 'ls -lrt'
            }
        }

        stage('Amazon Project') {
            steps {
                dir('Amazon') {
                    echo 'Inside Amazon Project'
                    sh 'pwd'
                }
            }
        }

        stage('SKY Project') {
            steps {
                dir('SKY') {
                    echo 'Inside SKY Project'
                    sh 'pwd'
                }
            }
        }

        stage('SpringCore Project') {
            steps {
                dir('SpringCore') {
                    echo 'Inside SpringCore Project'
                    sh 'pwd'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline execute successfully'
        }

        failure {
            echo 'Pipeline execution failed'
        }
    }
}
