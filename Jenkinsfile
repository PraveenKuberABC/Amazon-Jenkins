pipeline {
agent any
  stages {
      stage {'Maven test'} {
          steps {
              sh 'mvn clean test'
          }
      }
    }
    stage {'Maven Build'} {
          steps {
              sh 'mvn clean install'
          }
      }
    }

post {
    success {
        scho 'Pipeline completed successfully'
    }
    failure {
        echo 'pipeline got failed'
    }
}
