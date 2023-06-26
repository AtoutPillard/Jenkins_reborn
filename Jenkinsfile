pipeline {
    agent any
    environment {
	dockerhub=credentials('docker')
    }
    stages {
        stage('Checkout') {
            steps {
		bat 'git branch -d staging'
		bat 'git checkout -b staging'
		bat 'git push -u origin staging'
            }
        }
        stage('Building'){
            steps{
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Testing'){
            steps{
                bat 'python -m unittest'
            }
        }
	stage('Deploying'){
            steps{
                bat 'docker build -t atoutp/mlops_tp5:latest .'
                bat 'docker run -d -p 8000:8000 atoutp/mlops_tp5:latest'
            }
        }
	stage('User Acceptance') {
	    steps{
		input {
                	message "Proceed to push to main"
                	ok "Yes"
            	}    
	    }
	}
	stage('Pushing and Merging'){
		parallel {
			stage('Pushing Image') {
			    steps {
				bat 'docker push atoutp/mlops_tp5:latest'
			    }
			}
			stage('Merging') {
			    steps {
				bat 'git checkout main'
				bat 'git merge origin/staging'
				bat 'git push -f origin main'
			    }
			}
		}
	}
    }
    post {
        always {
            bat 'docker logout'
        }
    }
}
