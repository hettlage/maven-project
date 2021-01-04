pipeline {
	agent any

	stages {
		stage("Build") {
			steps {
				sh '/apache-maven-3.6.3/bin/mvn clean package'
				sh "docker build -t tomcatwebapp:${env.BUILD_ID} ."
			}
		}
	}
}