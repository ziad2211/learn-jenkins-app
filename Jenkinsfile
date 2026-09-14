pipeline{
    agent{
        docker {
            image 'node:18-alpine'
            reuseNode true
        }
    }
    stages{
        stage("Build"){
            steps{
                sh '''
                    echo "========Hello from Github!======="
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
        stage("Test"){
            steps{
                sh '''
                    echo "========Test Stage========"
                    test -f build/index.html
                    npm test
                '''
            }
        }
    }
}