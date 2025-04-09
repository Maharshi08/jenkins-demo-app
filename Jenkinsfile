pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo '🛠️ Building Docker image...'
                sh 'docker build -t jenkins-demo-app .'
            }
        }

        stage('Test') {
            steps {
                echo '🧪 Testing the app (placeholder)...'
                sh 'echo "No tests defined yet."'
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deploying Docker container...'
                sh 'docker run -d -p 3000:3000 jenkins-demo-app'
            }
        }
    }
}
