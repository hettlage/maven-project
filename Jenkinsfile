pipeline {
	agent any
		
	stages {
		stage('Build') {
			steps {
				sh '/apache-maven-3.6.3/bin/mvn clean package'
			}
			post {
				success {
					echo 'Now archiving...'
					archiveArtifacts artifacts: '**/target/*.war'
				}
			}
		}
		stage('Deploy to staging') {
			steps {
				build job: 'deploy-to-Staging'
			}
		}
		stage('Deploy to production') {
			steps {
				timeout(time: 5, unit: 'DAYS') {
					input message: 'Approve PRODUCTION deployment'
				}
			}
			post {
				success {
					echo 'Code deployed'
				}
				failure {
					echo 'Deployment failed'
				}
			}
		}
	}
}