pipeline {

    agent any

    environment {
        git_branch = 'main'
        git_url_praveen = 'https://github.com/PraveenKuberABC/Amazon-Jenkins.git'
    }

    stages {

        stage('CLONE PROJECT') {
            steps {
                git branch: "${git_branch}",
                    url: "${git_url_praveen}"
            }
        }

        stage('COMPILE') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('BUILD') {
            steps {
                sh 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo 'Build successful!'
        }

        failure {
            echo 'Build failed!'
        }
    }
}
