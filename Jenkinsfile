pipeline {
	agent any
	
	stages {
	    

      
      // Build the artefact
        stage('package') {
            steps {
                sh 'mvn clean package'
            }
        }
      
      
		
		// Deploy the artefact into the artefactory (Nexus) 
		stage('deploy'){
			steps {
				sh "echo 'deploying the artefact to Nexus'"
			}
		}
      
      
	}
  
	
	post {
		success {
		  sh "echo 'success'"
		  // Send Success Email 
		}
		failure {
		  sh "echo 'failure'"
		  // Send Failure Email 
		}
	}
}








