node {
	stage('Checkout') {
		echo 'Getting source code...'
		checkout scm
	}
  // def testimage  = docker.build("test-image")
  try {
    sh 'echo PWD is : $PWD'
    sh 'docker run --rm test-image cat /workdir/path/results/my-test-output.xml > $PWD/results/file2.xml'
  } finally {
    echo 'Finally...'
  }


}

