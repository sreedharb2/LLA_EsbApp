pipeline {
	agent any
	
	stages {
	    

      
      // Build the artefact
        stage('package') {
            steps {
                sh 'mvn clean package'
            }
        }
      
      stage('bitbucket deploy2') {
        steps {
          script{
	 		GIT_CREDS = credentials('bitbucket-server-cred')
            sh '''
                echo "${WORKSPACE}"
				cd ${WORKSPACE}
                
            '''
          }
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
