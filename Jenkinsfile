pipeline{
    agent any
    stages{
        stage("Build"){
            agent{
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps{
                
                sh '''
                    echo "========Hello from Github!======="
                    docker images
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}