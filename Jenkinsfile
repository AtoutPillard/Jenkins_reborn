pipeline {
    agent any
    environment { 
      DOCKER_ID = "dstdockerhub"
      DOCKER_IMAGE = "datascientestapi"
      DOCKER_TAG = "v.${BUILD_ID}.0" 
    }
    stages {
        stage('Building') {
          steps {
 		sh 'python3 -m pip install -r requirements.txt'
           }
	}
	stage('Unit Testing') {
          steps {
    		sh 'python3 -m unittest'
           }
	}
	stage('Deploying with Docker') {
          steps{
            script {
              sh '''
              docker rm -f jenkins
              docker build -t $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG .
              docker run -d -p 8000:8000 --name jenkins $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG
              '''
            }
          }
        }
	stage('User Acceptance') {
          input {
            message "Proceed to push to Dockerhub"
            ok "Yes"
          }
          steps{
            echo 'Accepted'    
	        }
	      }
	      stage('Pushing and Merging'){
	        parallel {
		        stage('Docker Push') {
		          environment {
			          DOCKERHUB_CREDENTIALS = credentials('docker_jenkins')
		          }
		          steps {
				script {
                		sh'''
		  		echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin
			        docker push $DOCKER_ID/$DOCKER_IMAGE:$DOCKER_TAG
	   			'''
		          	}
		        }
			}
		    stage('Merging') {
		      steps {
			echo 'Merging done'
		      }
		    }
	      }
	    }
    }
    post {
      always {
        sh 'docker logout'
      }
    }
}
