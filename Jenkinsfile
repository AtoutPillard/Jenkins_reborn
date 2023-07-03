pipeline {
    agent any
    environment {
    	dockerhub = credentials('docker_jenkins')
    }
    stages {
        stage('Building') {
		agent {
                docker {
                    image 'python:3.8-alpine3.16'
                }
            }
            steps {
		withEnv(["HOME=${env.WORKSPACE}"]) {
	    	sh 'pip install -r requirements.txt'
		}
            }
        }
        stage('Testing') {
            steps {
	    	sh 'python -m unittest'
            }
        }
	stage('Deploying') {
            steps{
	    	script {
		sh '''
		docker build -t dst_dockerhub/dst_api:latest .
		docker run -d -p 8000:8000 dst_dockerhub/dst_api:latest
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
				sh 'docker push dst_dockerhub/dst_api:latest'
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
