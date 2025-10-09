pipeline {
    agent any 
       stages {
          stage('checkout') {
            steps {
                echo 'pulling the repository'
                git branch: 'master', url: 'https://github.com/Shashank-1202/simple-node-jenkins-demo.git'

            }
          }

            stage('build') {
                steps {
                    echo 'building the image'
                    sh 'docker build -t simple-node1 .'

                }
            }

            stage('Deploy') {
                steps {
                    echo 'deploying the image'
                    sh '''
                      docker rm -f simple-node1 || true
                      docker run -d -p 80:80 --name simple-node1 simple-node1
                    '''
                }
            }

       }
}
