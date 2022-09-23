node {   
    stage('Clone repository') {
        git credentialsId: 'git', url: 'https://github.com/Dikshatr/Sample.github.io.git'
    }
    
    stage('Build image') {
       dockerImage = docker.build("dikshatrdocker/sampledocker")
    }
    

stage('Push image') {
        withDockerRegistry([ credentialsId: "docker", url: "https://hub.docker.com/repository/docker/dikshatrdocker/sampledocker" ]) {
        dockerImage.push()
        }
    }    
}
