pipeline{
	
   agent any
	
	tools{
		maven 'maven3.8.4'
	}
	
     stages{
        
        stage('git clone'){
		steps{

              git credentialsId: 'GIT-HUB-CREDENTIALS', url: 'https://github.com/bpavani1992/java-k8s-deploy.git'
	       }
	}
	stage('build'){
		steps{

	   sh " mvn clean package "
		}
	}
	     
       stage('docker image'){
	       steps{

       sh " docker build -t bpavani19992/java-web-app:latest . "
	       }
       }
       }
}

