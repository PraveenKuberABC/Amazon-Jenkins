pipeline {
    agent any
    environment {
        // Use PATH+EXTRA to append to PATH properly
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
        stage('Deploy'){
            when {
                expression { 
                    env.BRANSH_NAME?.CONTAINS('release')
                }
            }
            steps{
                echo "Its release baranch, it'll deploy to tomcat"
            }
        } 
    }

  post{

  success{
     echo 'Build success'
  }
    
  failure{
       echo 'Failure in the build'
   }
  }
}
