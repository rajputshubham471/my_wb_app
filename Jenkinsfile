pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url:'https://github.com/rajputshubham471/my_wb_app.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building website..."
                // For static website, no build needed, but if React/Node:
                // sh 'npm install && npm run build'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                // sh 'npm test'   # optional if you have tests
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying website..."
                // Example: copy files to Apache/Nginx web dir
                sh 'cp -r * /var/www/html/'
            }
        }
    }

    post {
        success {
            echo "✅ Website deployed successfully!"
        }
        failure {
            echo "❌ Deployment failed!"
        }
    }
}
