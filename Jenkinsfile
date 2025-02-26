pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/Farhan22-sudo1/PIPELINE1.git'
        BRANCH = 'main'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: "${BRANCH}", url: "${REPO_URL}"
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add build commands here
                // Example for Node.js: sh 'npm install'
                // Example for Java: sh './gradlew build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add test commands here
                // Example for Node.js: sh 'npm test'
                // Example for Java: sh './gradlew test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add deployment steps here
                // Example: sh 'scp -r * user@server:/path/to/deployment'
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
