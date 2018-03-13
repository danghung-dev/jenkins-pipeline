pipeline {
    agent { docker { image 'node:6.3' } }
    stages {
        stage('build') {
            steps {
				echo 'Building dependencies...'
       		 	sh 'npm install'
            }
        }
		stage('Test') {
			steps {
				echo 'Testing...'
				sh 'npm test'
			}
		}

		stage('Publish') {
			steps {
				echo 'Publishing Test Coverage...'
				publishHTML (target: [
					allowMissing: false,
					alwaysLinkToLastBuild: false,
					keepAll: true,
					reportDir: 'coverage/lcov-report',
					reportFiles: 'index.html',
					reportName: "Application Test Coverage"
				])
			}
		}
    }
}
