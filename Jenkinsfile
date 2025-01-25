node {
    stage('Clone repository') {
        git credentialsId: 'github-access-token', url: 'https://github.com/ktemple77/web-count.git'
    }

    stage('Build image') {
       dockerImage = docker.build("ktemple77/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
