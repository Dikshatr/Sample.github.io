node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

      checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Dikshatr/Sample.github.io.git']]])
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */
        
        dockerImage = docker build ("dikshatrdocker/sampledocker:latest")
        
    }

    

    stage('Push image') {
        /* Finally, we'll push the image with two tags:
         * First, the incremental build number from Jenkins
         * Second, the 'latest' tag.
         * Pushing multiple tags is cheap, as all the layers are reused. 
         *docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials'*/
           sh 'sudo docker login -u "dikshatrdocker" -p "dckr_pat_pfOXrr0oNmCtxMnF6YiS819_FS0" docker.io'
               
        app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        
   
    }
}
