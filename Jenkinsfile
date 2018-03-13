node {
	stage('Checkout') {
		when {
			branch 'production'
		}
		echo 'Getting source code...'
		checkout scm
		def testimage  = docker.build("test-image")
		testimage.inside {
			withEnv([
					'HOME=.',
			]) {
				echo 'Building dependencies...'
				sh 'npm install'
				echo 'Testing...'
				sh 'npm test'
			}
		}
	}
}

