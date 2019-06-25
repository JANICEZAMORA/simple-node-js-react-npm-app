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
        steps {
                sh 'https://github.com/JANICEZAMORA/simple-node-js-react-npm-app.git/jenkins/scripts/test.sh' 
            }
        }
    }
}
