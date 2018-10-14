node{
   stage('SCM Checkout'){
     git 'https://github.com/batibm/Bat.git'
   }
    stage('Compile-Package'){
        // Get maven home path
        def mvnHome = tool name: 'Maven', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
    }

    stage('SonarQube Analysis'){
         def mvnHome = tool name: 'Maven', type: 'maven'
         withSonarQubeEnv('SonarQube') {
            sh "${mvnHome}/bin/mvn sonar:sonar"
         }
    }

    stage('Docker Build') {
         
         app = docker.build("helloword/hello")		 
		 }
	} 
