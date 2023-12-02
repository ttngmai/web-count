node {
	stage('Clone repository') {
		git credentialsId: 'github_access_token', url: 'https://github.com/ttngmai/web-count.git'
	}
	stage('Build image') {
		dockerImage = docker.build("mweapon/web_count:v2.0")
	}
	stage('Push image') {
		withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
			dockerImage.push()
		}
	}
}
