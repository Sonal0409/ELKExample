node {
	def application = "springbootapp"
	

	stage('Clone repository') {
		checkout scm
	}

	stage('Build image') {
		sh 'docker build -t ${application}:${BUILD_NUMBER} .'
	}


	stage('Deploy') {
		sh ("docker run -d -p 81:8080 -v /var/log/:/var/log/ ${application}:${BUILD_NUMBER}")
		
	}

	
}
