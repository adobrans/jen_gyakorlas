pipeline {
    agent any
	environment {
		NEW_VERSION = '1.3.0'
	}
    stages {
        stage("build") {
            steps {
                echo "Build the app ${NEW_VERSION}"
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
