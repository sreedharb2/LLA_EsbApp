pipeline {
	agent any
	
	stages {
	    

      
      // Build the artefact
        stage('package') {
            steps {
                bat 'mvn clean package'
            }
        }
      
	}
  
	
	post {
		success {
		  bat "echo 'success'"
		  // Send Success Email 
		}
		failure {
		  bat "echo 'failure'"
		  // Send Failure Email 
		}
	}
}
