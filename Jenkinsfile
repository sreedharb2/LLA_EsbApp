pipeline {
	agent any
	
	stages {
	    

      
      // Build the artefact
        stage('package') {
            steps {
                sh 'mvn clean package'
            }
        }
      
      stage('bitbucket deploy') {
        steps {
          script{
	 		GIT_CREDS = credentials('bitbucket-server-cred')
            sh '''  
				cd /var/lib/jenkins/workspace/bitbucket_deploy2/target
                
                git init
                git config --global user.name "admin"
                git status
                git remote --verbose
                git remote add origin http://admin:admin123@34.242.48.107:7990/scm/or/ecom-ux.git
                git remote --verbose
                git pull origin master --allow-unrelated-histories
                git add -f *.jar
                git pull origin master --allow-unrelated-histories
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
