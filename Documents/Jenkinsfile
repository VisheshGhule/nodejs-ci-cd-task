pipeline {
    agent any

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
                echo 'Deployment stage - you can customize this'
                sh 'docker build -t visheshghule/nodejs-demo-app:latest .'
                // Uncomment the next line if DockerHub login is already configured on Jenkins
                // sh 'docker push visheshghule/nodejs-demo-app:latest'
            }
        }
    }
}

