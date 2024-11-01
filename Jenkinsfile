pipeline {
    agent any

    stages {
        stage('w/i dicjer') {
            steps {
                sh '''
                    echo "Sem docker"
                    ls -la
                    touch container-no.txt
                '''
                
            }
        }
        stage('w/ docker') {
            agent{
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "Com docker"
                    ls -la
                    npm --version
                    touch container-yes.txt
                '''
            }
        }
    }
}
