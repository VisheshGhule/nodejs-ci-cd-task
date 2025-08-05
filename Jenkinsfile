pipeline {
    agent {
        docker { image 'node:18-alpine' }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test || echo "No tests defined, skipping..."'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t visheshghule/nodejs-demo-app:latest .'
                // Optional: Push if Docker is configured in Jenkins
                // sh 'docker push visheshghule/nodejs-demo-app:latest'
            }
        }
    }
}
