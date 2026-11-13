pipeline {
    agent any
    
    environment {
        // Use PATH+EXTRA to append to PATH properly data
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }

    
    stages {

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
