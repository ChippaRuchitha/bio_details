pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {

                echo "Cloning repo..."
                checkout scm

                git 'https://github.com/ChippaRuchitha/bio_details.git'

            }
        }

        stage('Build') {
            steps {
                echo "Building Docker image..."
                sh 'docker build -t my-app .'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh './run-tests.sh'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying..."
                sh './deploy.sh'
            }
        }
    }
}

