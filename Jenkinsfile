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
				cd ${WORKSPACE}/target


                git init
                git config --global user.name "Administrator"
                git config --global user.email "nowsudheer@gmail.com"
                git status
                git remote add origin http://admin:admin123@34.242.48.107:7990/scm/or/lla-esb-artifactory.git
                git pull origin master --allow-unrelated-histories
                git add -A -f *.jar
                git status
                git commit -a -m "push into bitbucket"
                git push -f origin master

                
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
