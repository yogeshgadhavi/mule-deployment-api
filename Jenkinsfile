pipeline {
  agent any
  stages {
     stage('Build API') {
      steps {
        bat 'mvn install -Denvironment=dev'
      }
    }
    stage('Promote builds to artifactory') {
      def server = Artifactory.server 'ART-2'
        def uploadSpec = """{
            "files": [
                {
                    "pattern": "**/target/*.jar",
                    "recursive": "false",
                    "target": "mulesoft/",
                    "flat" : "false"
                }
            ]
        }"""
        
        def buildInfo1 = server.upload(uploadSpec)
        buildInfo1.retention maxBuilds: 10
        server.publishBuildInfo(buildInfo1)
   
    }
  }
     
 
}
