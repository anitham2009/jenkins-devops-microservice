//DECLARATIVE
pipeline {
	agent any
	//agent {docker { image 'maven:3.6.3'}}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "$PATH"
				echo "Build Number $env.BUILD_NUMBER"
				echo "Build ID $env.BUILD_ID"
				echo "Job Name $env.JOB_NAME"
				echo "Build Tag $env.BUILD_TAG"
				echo "Build URL $env.BUILD_URL"
			}
		}
		stage('Compile') {
			steps {
				sh 'mvn clean compile'
			}
		}	
		stage('Test') {
			steps {
				//echo "Test"
				sh 'mvn test'
			}
		}
		stage('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
				//echo "Integration Test"
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