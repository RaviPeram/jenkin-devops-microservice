//stage blocks are optional  node step
//scripted pipe line  node  
//DECLARATIVE pipeline > stages > stage > steps
pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				echo "Build"
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
			echo 'I will run always'
		}
		success {
			echo 'i will run only you are successful'
		}
		failure {
			echo 'i will run when you are failure'
		}
	}
}
