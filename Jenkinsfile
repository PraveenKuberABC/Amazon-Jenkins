pipeline {
    agent any 
      stages {
          stage('compile') {
              steps {
                  sh 'mvn clean'
              }
          }
          stage('build') {
              steps {
                  sh 'mvn clean install'
              }
          }
          stage('Deploy') {
              when {
                  expression {
                      env.BRANCH_NAME?.contains('release')
                  }
              }
              steps {
                echo "Its an release branch and will start deploy the war to tomcat"
              }
          }
      }
    post {
        success {
            echo 'Build Success 1'
        }
        failure {
            echo 'failure in the build'
        }
    }
}
