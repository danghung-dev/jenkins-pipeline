
		node {
			def testimage  = docker.build("test-image")
			testimage.inside {
				stage('Checkout') {
					steps {
						echo 'Getting source code...'
						checkout scm
					}
				}
				steps {
					echo 'Building dependencies...'
					sh 'npm install'
					echo 'Testing...'
					sh 'npm test'
				}
			}
		}

