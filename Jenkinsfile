
pipeline {
  agent any
  stages {
     stage('Build image') {
      steps {
        echo 'Starting to build docker image'
        script {
           def  app = docker.build(" Pipeline-Image:${env.BUILD_ID}")
        }
      }
    }
        stage('Push image') {
            docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
            }
        }
    }
}         

    
   


   
   
  


       
   
  
  


                            
