pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                bat 'https://github.com/fulldrill/resumeappwin.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t resume-app:latest ./app'
            }
        }

      stage('Run Container') {
            steps {
                bat '''
                docker rm -f resume-app || true
                docker run -d -P --name resume-app resume-app:latest
                '''
            }
        }

    }
}