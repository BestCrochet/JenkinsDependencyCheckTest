pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git 'C:\\SIT\\Year 3\\3203\\Lab6\\JenkinsDependencyCheckTest'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}