pipeline {
    agent any
    environment {
        // Use PATH+EXTRA to append to PATH properly iteam 
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }
    stages {

        stage('pull scm git ') {
            steps {
                git branch: 'main', url: 'https://github.com/PraveenKuber/Amazon-Jenkins.git'
            }
        }
        stage('compile stage  ') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('build stage ') {
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
