pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'echo Building Portfolio Website'
            }
        }

        stage('List Files') {
            steps {
                bat 'dir'
            }
        }
    }
}