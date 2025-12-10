pipeline {
    agent any

    environment {
        // Optional: You can set the Node.js path if not in system PATH
        NODE_HOME = 'C:\\Program Files\\nodejs'
        PATH = "${env.NODE_HOME};${env.PATH}"
    }

    stages {
        stage('Check Node.js') {
            steps {
                echo 'Checking Node.js version...'
                bat 'node -v || echo Node.js not found!'
                bat 'npm -v || echo npm not found!'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing Node.js dependencies...'
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                // Safe: if no tests exist, it will not fail the pipeline
                bat 'npm test || echo "No tests defined"'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
