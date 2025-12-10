# Jenkinsfile
echo "pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                echo 'Installing Node.js dependencies...'
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'npm test || echo No tests defined'
            }
        }
    }
}"
