pipeline {
    agent { docker { image 'node:6.3' } }
    stages {
        stage('build') {
            steps {
                 echo 'Building dependencies...'
       		 sh 'npm i'
            }
        }
	stage('Test') {
        	echo 'Testing...'
        	sh 'npm test'
    	}

    stage('Publish') {
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
