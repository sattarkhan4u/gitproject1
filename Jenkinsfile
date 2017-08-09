pipeline {
	agent {
		node {
			label 'java8'
		}
	}
	tools {
		maven 'm3'
	}
	stages {
		stage('Checkout') {
			steps {
				git 'https://github.com/bertjan/spring-boot-sample'
			}
		}
		stage('Build') {
			steps {
				sh 'mvn -B -V -U -e clean package'
			}
		}
		stage('Archive') {
			steps {
				junit(testResults: '**/target/**/TEST*.xml',allowEmptyResults: true)
			}
		}
	}
}
