pipeline {
    agent any
	environment {
		NEW_VERSION = '1.3.0'
	}
	parameters {
		choice (name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
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
                echo 'variables does not work in single quotes params.${VERSION}'
				echo "Testing the app params.${VERSION}"
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
