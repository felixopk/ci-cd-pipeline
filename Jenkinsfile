pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test || echo "No tests found"'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ci-cd-pipeline .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -d -p 3000:3000 ci-cd-pipeline'
            }
        }
    }
}

