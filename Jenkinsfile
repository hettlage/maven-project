pipeline {
	agent any
		
	parameters {
		string(name: 'staging_server', defaultValue: '127.0.0.1', description: 'Staging server')
	}

	triggers {
		pollSCM('* * * * *')
	}

	stages {
		stage('Deployments') {
			parallel {
		        stage('Deployment to staging server') {
			        sh "Deploying to staging server"
			    }
			    stage('Deployment to production server') {
			        sh "Deploying to production server"
			    }
			}
		}
	}
}