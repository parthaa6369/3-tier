pipeline {
    agent any

    environment {
        PROJECT_DIR = "/home/ubuntu/3-tier"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/parthaa6369/3-tier.git'
            }
        }

        stage('Build & Deploy') {
            steps {
                sh '''
                cd $PROJECT_DIR

                docker-compose down || true

                docker-compose up -d --build
                '''
            }
        }
    }
}
