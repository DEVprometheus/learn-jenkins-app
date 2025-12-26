pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    args '-u root:root'
                }
            }
            steps {
                sh '''
                    # Workspace'i tamamen temizle
                    rm -rf node_modules package-lock.json
                    
                    # Checkout yap (container içinde)
                    git clone https://github.com/DEVprometheus/learn-jenkins-app.git app
                    cd app

                    ls -la
                    node --version
                    npm --version
                    npm install
                    npm build
                    ls -la
                '''
            }
        }
    }
}
