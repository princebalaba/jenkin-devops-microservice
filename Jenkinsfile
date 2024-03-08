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
	//agent any
	//agent { docker { image 'maven:3.6.3' } }
	agent { docker { image 'node:latest' } }
	stages {
		stage ('Build') {
			steps {
				//sh 'mvn --version'
				sh 'node --version'
				echo "Build"
				
			}
		}
		stage ('Test') {
			steps {
				
				echo "Test"
				
			}
		}
		stage ('Integration Test') {
			steps {
				
				echo "Integration Test"
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
