pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        
        stage('Push image') {
        /* Finally, we'll push the image with two tags:
         * First, the incremental build number from Jenkins
         * Second, the 'latest' tag.
         * Pushing multiple tags is cheap, as all the layers are reused. 
         *docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials'*/
           sh 'sudo docker login -u dikshatrdocker -p "dckr_pat_QfwFxJSZ-5K_PEi-XpgcXt-QpAw" docker.io'
               
        app.push("${env.BUILD_NUMBER}")
            app.push("latest")
    }
    
   
}
