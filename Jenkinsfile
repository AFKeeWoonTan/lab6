pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git '/home/Documents/cloak.pte.ltd/projects-docs/SIT/notes/Lab/lab6/JenkinsDependencyCheckTest'
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
