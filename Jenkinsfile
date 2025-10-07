pipeline {
    agent any 
    stages {
        stage('checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Shashank-1202/simple-node-jenkins-demo.git'    
            }
        }
        stage('build') {
           steps {
              sh 'docker build -t simple-node:${BUILD_NUMBER} .'
           }
        }
        stage('Run container') {
            steps {
                sh '''
                     docker rm-f simple-node || true
                     docker run -d -p 8080:8080 --name simple-node simple-node:${BUILD_NUMBER}
                '''     
            }

        }
    }
}
