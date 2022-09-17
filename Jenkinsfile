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
    }
    
    post 
    {  
        always
        {
            emailext body: 'Build Pipeline Success', subject: 'Build Pipeline Success', to: 'diksha1999tripathi@gmail.com'
        }
    }
}
