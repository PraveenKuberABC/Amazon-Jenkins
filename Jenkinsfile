@Library('my-shared-lib') _
pipeline {
    agent any
    environment { 
        // Use PATH+EXTRA to append to PATH properly
        PATH = "/usr/bin:/bin:/usr/local/bin"
    }
    stages {

        //stage('pull scm git ') {
          //  steps {
            //    git branch: 'main', url: 'https://github.com/twinklefornewtech/Amazon-Jenkins.git'
            //}
        //}
        stage('compile ') {
            steps {
                buildMaven()
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
