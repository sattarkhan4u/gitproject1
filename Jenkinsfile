pipeline {
	agent any
	
	stages {
		stage('Compile Stage') {
			steps {
				mvnTool = tool 'm3' {
					sh 'mvn clean compile'
				}
			}
		}
		stage('Testing Stage') {
			steps {
				mvnTool = tool 'm3' {
					sh 'mvn test'
				}
			}
		}
		stage('Deployment Stage') {
			steps {
				mvnTool = tool 'm3' {
					sh 'mvn deploy'
				}
			}
		}
	}
}
