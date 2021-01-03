pipeline {
	agent any
		
	parameters {
		string(name: 'staging_server', defaultValue: '127.0.0.1', description: 'Staging server')
		string(name: 'production_server', defaultValue: '127.0.0.2', description: 'Production server')
	}

	triggers {
		pollSCM('* * * * *')
	}

	stages {
		stage('Deployments') {
			parallel {
		        stage('Deployment to staging server') {
		        	steps {
			            sh "Deploying to ${params.staging_server}"
			        }
			    }
			    stage('Deployment to production server') {
			    	steps {
			            sh "Deploying to ${params.production_server}"
			        }
			    }
			}
		}
	}
}