pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pull code from GitHub
                git url: 'https://github.com/Farhan22-sudo1/PIPELINE1.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                // Run tests
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the app (for example, using SCP to transfer files)
                sh 'scp -r ./dist/* user@server:/var/www/html'
            }
        }
    }

    post {
        always {
            // Clean up workspace after pipeline is done
            cleanWs()
        }
    }
}
