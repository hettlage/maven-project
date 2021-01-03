pipeline {
	agent any

	stages {
		stage("Build") {
			steps {
				step {
					sh '/apache-maven-3.6.3/bin/mvn clean package'
				}
			}
		}
	}
}