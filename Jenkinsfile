pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/Farhan22-sudo1/PIPELINE1.git'
        BRANCH = 'main'
    }

    tools {
        nodejs 'NodeJS' // Ensure Jenkins is configured with a NodeJS tool named 'NodeJS'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: "${BRANCH}", url: "${REPO_URL}"
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deployment steps here
                // Example: sh 'scp -r * user@server:/path/to/deployment'
                // Or use a CI/CD tool/service to handle deployment
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            cleanWs()
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs for more details.'
        }
    }
}
