//stage blocks are optional  node step
//scripted pipe line  node  
//DECLARATIVE pipeline > stages > stage > steps
pipeline {
	  agent any
	//agent { docker { image 'maven:3.6.3'} }
	tools{
		'org.jenkinsci.plugins.docker.commons.tools.DockerTool' '18.09'
	}
	environment{
		//dockerHome = tool 'myDocker'
		DOCKER_CERT_PATH = credentials('id-for-a-docker-cred')
		mavenHome = tool 'myMaven'
		//PATH = "$mavenHome/bin:$PATH"
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Build') {
			steps {
				sh 'mvn --version'
				sh 'docker version'// DOCKER_CERT_PATH is automatically picked up by the Docker client
				echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"

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
