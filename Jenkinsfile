pipeline {
     stages{
        
        stage('git clone') {

              git credentialsId: 'GIT-HUB-CREDENTIALS', url: 'https://github.com/bpavani1992/java-k8s-deploy.git'
	       }
	stage('build') {

	sh mvn clean package

	}
       stage('docker image') {


       sh docker build -t bpavani19992/java-web-app:latest .



}
       }

