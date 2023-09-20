pipeline {
    agent any
    stages {
        stage('Name Branch') {
          steps {
		sh "echo 'This is the branch named ${env.GIT_BRANCH}'"
	  }
	}
    }
}
