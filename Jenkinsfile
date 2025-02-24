node {
	def application = "springbootapp"
	

	stage('Clone repository') {
		checkout scm
	}

	stage('Build image') {
		sh 'docker build -t myimagespring:${BUILD_NUMBER} .'
	}


	stage('Deploy') {
		sh ("docker run -d -p 81:8080 -v /var/log/:/var/log/ myimagespring:${BUILD_NUMBER}")
		
	}

	
}
