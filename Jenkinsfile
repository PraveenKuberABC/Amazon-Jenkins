pipeline {
    agent any
    environment {
        
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
stage('deploy'){
    when{
        expression{
            env.BRANCH_NAME?contains('release-branch')
        }
    }
    steps{
        echo "Its an release-branch branch and will start deploy the war to tomcat"
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
