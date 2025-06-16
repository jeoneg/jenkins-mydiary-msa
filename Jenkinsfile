node {
	stage('Clone repository') {
		git branch: 'main',
			credentialsId: 'github_access_token',
			url: 'https://github.com/jeoneg/jenkins-mydiary-msa.git'
	}

	stage('Build image') {
		dockerImage = docker.build("wjsyuwls/mydiary-front:2.0")
	}

	stage('Push image') {
		withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
			dockerImage.push()
		}
	}
}
