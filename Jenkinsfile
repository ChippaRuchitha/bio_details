ChatGPT said:

Perfect 👌 Let’s update your Jenkinsfile so it:

Clones your repo (with Bio.html + Dockerfile).

Builds the Docker image.

Runs the container (serving your Bio page with nginx).

Here’s a working Jenkinsfile for your case:
pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo "Cloning repository..."
                git branch: 'main', url: 'https://github.com/ChippaRuchitha/bio_details.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo "Building Docker image..."
                sh 'docker build -t bio-app .'
            }
        }

        stage('Run Container') {
            steps {
                echo "Running Docker container..."
                // Stop & remove old container if already running
                sh '''
                docker stop bio-container || true
                docker rm bio-container || true
                docker run -d --name bio-container -p 8085:80 bio-app
                '''
            }
        }
    }
}
