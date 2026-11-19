pipeline {
    agent any
    environment {
    
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }
    stages {
stage('check files') {
    steps {
        sh 'pwd'
        sh 'ls' 
    }
}
        stage('pull scm git ') {
            steps {
                git branch: 'main', url: 'https://github.com/monishamonimp3-7373/Amazon-Jenkins.git'
            }
        }
        stage('compile ') {
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

  post{

  success{
     echo 'Build success 1'
  }
    
  failure{
       echo 'Failure in the build'
   }

  }


}
