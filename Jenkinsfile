node {
     
    def mvnHome = tool 'Maven 3'
    // holds reference to docker image
    def dockerImage
    // ip address of the docker private repository(nexus)
 
    def dockerImageTag = "devopsexample${env.BUILD_NUMBER}"
    
    stage('Clone Repo') 
    { 
      git 'https://github.com/shipra-trivedi/DevOps-Example.git'         
      mvnHome = tool 'Maven 3'
    }    
  
   stage('Build'){
        echo "Into Build"
        sh "${mvnHome}/bin/mvn clean install -f pom.xml"
          }
		
    stage('Build Docker Image') {
      // build docker image
      dockerImage = docker.build("devopsexample:${env.BUILD_NUMBER}")
    }
}
