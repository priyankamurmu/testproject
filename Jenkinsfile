node {
	

	stage('Clone repository') {
		checkout scm
	}

	stage('Build image') {
		app = docker.build("testproject")
	}

	stage('Deploy') {
		sh ("docker run -d -p 80:8181 -v /var/log/:/var/log/ testproject")
	}
	
	stage('Remove old images') {
		// remove docker old images
		sh("docker rmi testproject:latest -f")
   }
}
