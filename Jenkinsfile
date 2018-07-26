pipeline {
  agent any
  stages {
     stage('Build API') {
      steps {
        bat 'mvn install -Denvironment=dev'
      }
    }
    
     stage('Upload Artifact') {
            steps {
                
                                 script {
                                        def server = Artifactory.newServer url: 'file:///C:/ANZ/Repositories/', credentialsId: 'mulesoft-artifactory'
                                        server.bypassProxy = true
                                        def buildInfo = server.upload
                                        }
                    
                }
            
        
    }
  }
 
}
