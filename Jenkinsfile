pipeline {
	agent any
	
	stages {
	    

      
      // Build the artefact
        stage('package') {
            steps {
                sh 'mvn clean package'
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
