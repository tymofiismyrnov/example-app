node {
	def app
	
	stage('Clone repository') {
		checkout scm
	}

	stage ('Build image') {
		app = docker.build('tymofiismyrov/example-app')
	}

	stage('Push image') {
		docker.withRegistry('https://registry.hub.doker.com', 'docker-hub-credentials') {
			app.push('latest')
		}
	}
}
