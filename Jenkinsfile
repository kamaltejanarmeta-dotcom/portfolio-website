pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t portfolio-website .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat '''
                docker stop portfolio 2>nul
                docker rm portfolio 2>nul
                exit /b 0
                '''
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d --name portfolio -p 8081:80 portfolio-website'
            }
        }
    }
}