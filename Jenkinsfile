pipeline {
    agent any
	environment {
		NEW_VERSION = '1.3.0'
	}
	parameters {
		string (name: "VERSION", default value: '', description: 'version to deploy')
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
