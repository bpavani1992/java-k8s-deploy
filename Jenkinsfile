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

                        sh " docker build -t bpavani/java-web-app:latest . "
	               }
          }
	   stage('docker login'){
		    
		 steps{
			     sh " docker login -u bpavani -p Thaswika17@ "
		       }
	   }
           stage(' docker push'){
			    
		 steps{
				    
			    sh " docker push bpavani/java-web-app:latest "
		       }
	    }
		
	     stage('deploy deployment.yml'){
		    
		     steps{
		             sh " kubectl apply -f deployment.yml "
		     }
	     }
	     stage(' deploy service.yml'){
			     steps{
				     sh " kubectl apply -f service.yml "
			     }
		     }
	     }
       }


