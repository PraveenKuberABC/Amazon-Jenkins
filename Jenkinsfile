pipeline {

    agent any

    environment {
        GIT_BRANCH = 'main'
        GIT_URL = 'https://github.com/uday1487/Amazon-Jenkins.git'
    }

    stages {

        stage('CLONE REPOSITORY') {
            steps {
                git branch: "${GIT_BRANCH}",
                    url: "${GIT_URL}"
            }
        }

        stage('BUILD AMAZON') {
            when {
                expression { fileExists('Amazon/pom.xml') }
            }
            steps {
                dir('Amazon') {
                    sh 'mvn clean install'
                }
            }
        }

        stage('BUILD SKY') {
            when {
                expression { fileExists('SKY/pom.xml') }
            }
            steps {
                dir('SKY') {
                    sh 'mvn clean install'
                }
            }
        }

        stage('BUILD SPRINGCORE') {
            when {
                expression { fileExists('SpringCore/pom.xml') }
            }
            steps {
                dir('SpringCore') {
                    sh 'mvn clean install'
                }
            }
        }

        stage('BUILD SPRINGDEMO') {
            when {
                expression { fileExists('SpringDemo/pom.xml') }
            }
            steps {
                dir('SpringDemo') {
                    sh 'mvn clean install'
                }
            }
        }

        stage('BUILD SPRINGNEW') {
            when {
                expression { fileExists('SpringNew/pom.xml') }
            }
            steps {
                dir('SpringNew') {
                    sh 'mvn clean install'
                }
            }
        }

        stage('BUILD TEST') {
            when {
                expression { fileExists('Test/pom.xml') }
            }
            steps {
                dir('Test') {
                    sh 'mvn clean install'
                }
            }
        }
    }

    post {
        success {
            echo 'All available Maven projects built successfully!'
        }

        failure {
            echo 'One or more project builds failed!'
        }
    }
}
