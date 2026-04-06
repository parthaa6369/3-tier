pipeline {
    agent { label 'slave-1' }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/parthaa6369/3-tier.git'
            }
        }

        stage('Build & Deploy') {
            steps {
                sh '''
                pwd
                ls

                docker compose down || true
                docker compose up -d --build
                '''
            }
        }
    }
}
