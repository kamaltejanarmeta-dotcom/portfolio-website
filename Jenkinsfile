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

        stage('Stop Existing Container') {
            steps {
                bat '''
                docker stop portfolio || exit /b 0
                docker rm portfolio || exit /b 0
                '''
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d --name portfolio -p 8081:80 portfolio-website'
            }
        }
    }
}