pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: 'github-token', url: 'https://github.com/jyothi-surya/webdevlopment.git'
            }
        }

        stage('Lint JavaScript') {
            steps {
                sh 'npm install -g eslint || true'  // Install ESLint if not available
                sh 'eslint script.js || true'  // Run ESLint, ignore errors
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying files...'
                sh 'cp -r * /var/www/html/currency-converter/'  // Example: Copy files to Apache server
            }
        }
    }
}
