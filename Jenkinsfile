//Scrited pipeline
// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 		echo "Integration Test"
// 	}

// }

// Declarative pipeline
pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3' } }
	//agent { docker { image 'node:latest' } }
	environment {
		mavenHome = tool 'myMaven'
		dockerHome = tool 'myDocker'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage ('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				//sh 'node --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_NAME - $env.BUILD_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
				
			}
		}
		stage('Compile') {
			steps {
				sh "mvn clean compile"
			}

		}
		stage ('Test') {
			steps {
				
				sh "mvn test"
				
			}
		}
		stage ('Integration Test') {
			steps {
				
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
	} 
	post { //[always, changed, fixed, regression, aborted,
	       // success, unsuccessful, unstable, failure, notBuilt, cleanup]
		always {
			echo 'Im so awesome. I run all the time haha!!!'
		}
		success {
			echo 'Im so awesome. I when you are sucessful!!!'
		}
		failure {
			echo 'Im so awesome. I run when you fail!!!'
		}
	}
}
