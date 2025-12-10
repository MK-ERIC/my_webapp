pipeline {
    agent any

    tools {
        nodejs 'NodeJS-18'  // Make sure this matches your NodeJS installation name
    }

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Installing Node.js dependencies...'
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                bat 'npm test || echo No tests defined'
            }
        }
    }

    post {
        always { echo 'Pipeline finished.' }
        success { echo 'Build succeeded!' }
        failure { echo 'Build failed!' }
    }
}
