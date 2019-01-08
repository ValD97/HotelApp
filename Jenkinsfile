pipeline {
	agent any

	stages {
		stage('Build') {
			steps {
				mvn install -DskipTests=true -Dmaven.javadoc.skip=true -B -V
			}
		}
		stage('Test') {
			steps {
				mvn test -B
			}
		}
	}
}
