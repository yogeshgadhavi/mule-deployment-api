pipeline {
  agent any
  stages {
     stage('Build API') {
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      }
      steps {
        bat 'mvn install -Denvironment=dev'
      }
    }
    }
}
