node {
	stage('Checkout') {
		echo 'Getting source code...'
		checkout scm
	}
	if (env.BRANCH_NAME == 'dev') {
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
	} else {
		echo "Day khong phai la branch dev nen khong lam gi ca "
	}

}

