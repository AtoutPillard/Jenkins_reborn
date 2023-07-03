pipeline {
    agent any
    environment {
    	dockerhub = credentials('docker_jenkins')
    }
    stages {
        stage('Building') {
            steps {
	    	sh 'pip install -r requirements.txt'
            }
        }
        stage('Testing') {
            steps {
	    	sh 'python3 -m unittest'
            }
        }
	stage('Deploying') {
            steps{
	    	script {
		sh '''
		docker build -t dstDockerhub/dst_api:latest .
		docker run -d -p 8000:8000 dstDockerhub/dst_api:latest
		'''
		}
            }
        }
	stage('User Acceptance') {
		input {
                	message "Proceed to push to main"
                	ok "Yes"
            	}
		steps {
			echo 'Lets go'
		}
	}
	stage('Pushing and Merging'){
		parallel {
			stage('Pushing Image') {
			    steps {
				sh 'docker push dstDockerhub/dst_api:latest'
			    }
			}
			stage('Merging') {
			    when {
				branch 'development'
			    }
			    steps {
				script {
				sh '''
				git checkout main
				git merge origin/staging
				git push -f origin main
				'''
				}
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
