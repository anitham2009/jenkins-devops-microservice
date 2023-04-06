//DECLARATIVE
pipeline {
	agent any
	//agent {docker { image 'maven:3.6.3'}}
	stages {
		stage('Build') {
			steps {
				//sh 'mvn --version'
				echo "Build"
				echo "$PATH"
				echo "Build Number $env.BUILD_NUMBER"
				echo "Build ID $env.BUILD_ID"
				echo "Job Name $env.JOB_NAME"
				echo "Build Tag $env.BUILD_TAG"
				echo "Build URL $env.BUILD_URL"
			}
		}	
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}

	} 
	post {
		always {
			echo "I always run"
		}
		success {
			echo "I run when success"
		}
		failure {
			echo "I run when failure"
		}
	}
}