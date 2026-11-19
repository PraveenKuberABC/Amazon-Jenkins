pipeline {
    agent any
    environment {
        // Use PATH+EXTRA to append to this PATH properly
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }
    stages {

        stage('pull scm git') {
            steps {
                git branch: 'main', url: 'https://github.com/sapsoni-hue/Amazon-Jenkins'
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
