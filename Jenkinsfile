pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3002:3002' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
               }
        }
        stage('Test') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Terminaste de usar el sitio web? (Click "Proceed" para continuar)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
