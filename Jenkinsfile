pipeline {
    agent any
    stages {
        stage("build") {
            steps {
                echo 'Build the app...'
            }
        }
        stage("test") {
			when {
				expression {
					BRANCH_NAME == 'main' || BRANCH_NAME == 'master'
				}
			}
            steps {
                echo 'Testing the app...'
            }
        }
        stage("deploy") {
            steps {
                echo 'Deploying the app...'
            }
        }
    }
	post {
		always {
			echo 'will run everytime...'
		}
		failure {
			echo 'will only run when failed...'
		}
	}
}
