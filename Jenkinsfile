pipeline {
	agent any
	tools {
		maven 'maven'
	}
	stages {
		stage('Checkout') {
			steps {
				git branch: 'Main', url: 'https://github.com/hemanth3007/mvn-pipeline.git'
			}
		}
		stage('Build') {
			steps {
				sh 'mvn compile'
			}
		}
		stage('Test') {
			steps {
				sh 'mvn clean package'
			}
		}
		stage('Run Application') {
			steps {
				sh 'java -jar target/mvn-pipeline-1.0-SNAPSHOT.jar'
			}
		}
	}
	post {
		success {
			echo 'Build successful and deployed'
		}
		failure {
			echo 'Build failure'
		}
	}
}
