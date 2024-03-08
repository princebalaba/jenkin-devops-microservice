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
	stages {
		stage ('Build') {
			steps {
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
	post {
		always {
			echo 'Im so awesome. I run all the time haha!!!'
		}
		sucess {
			echo 'Im so awesome. I when you are sucessful!!!'
		}
		failure {
			echo 'Im so awesome. I run when you fail!!!'
		}
	}
}
