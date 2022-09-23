pipeline {
    agent any

    stages {
        
        stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }
        stage('Build') {
            steps {
             app = docker.build("dikshatrdocker/sampledocker")
           
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
                sh 'sudo docker login -u "dikshatrdocker" -p "dckr_pat_pfOXrr0oNmCtxMnF6YiS819_FS0" docker.io'
               
        app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        
            }
        }
        
 
    }
    
   
}
