node {
     
    def mvnHome = tool 'Maven 3'  
  //  def dockerImage
    registryName = "myjavaapp2"
    registryUrl = "mynewconreg.azurecr.io"
    registryCredential= "mynewconreg"
	
    def dockerImageTag = "devopsexample${env.BUILD_NUMBER}"
    
    stage('Clone Repo') 
    { 
      git 'https://github.com/KirtiPhirke98/DevOps-Example.git'         
      mvnHome = tool 'Maven 3'
    }    
  
   stage('Build'){
        echo "Into Build"
        sh "${mvnHome}/bin/mvn clean install -f pom.xml"
          }
		
     stage ('Build Docker image'){
        echo "Into buiding docker image"
        docker.build registryName
          }
	
	/*stage('ACR Push') {
        sh "az acr login -n mynewconreg --username mynewconreg --password e7WuJxuypxNedQn6Jlj0betVvZ=cFqXH"
        sh " docker tag myjavaapp2 mynewconreg.azurecr.io/myjavaapp2"
        sh " docker push mynewconreg.azurecr.io/myjavaapp2"
         }*/
	
}
