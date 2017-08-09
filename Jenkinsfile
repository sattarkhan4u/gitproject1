pipeline {
	agent any
	
	stages {
		stage('Compile Stage') {
			steps {
				mvnTool = tool 'me' {
					sh 'mvn clean compile'
				}
			}
		}
		stage('Testing Stage') {
			steps {
				mvnTool = tool 'me' {
					sh 'mvn test'
				}
			}
		}
		stage('Deployment Stage') {
			steps {
				mvnTool = tool 'me' {
					sh 'mvn deploy'
				}
			}
		}
	}
}
