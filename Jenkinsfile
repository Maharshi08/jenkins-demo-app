pipeline {
    agent any

    environment {
        IMAGE_NAME = 'maharshi86/jenkins-demo-app'
        TAG = 'latest'
    }

    stages {
        stage('Build') {
            steps {
                echo '🛠️ Building Docker image...'
                sh 'docker build -t $IMAGE_NAME:$TAG .'
            }
        }

        stage('Test') {
            steps {
                echo '🧪 Testing the app (placeholder)...'
                sh 'echo "No tests defined yet."'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                echo '📤 Pushing Docker image to Docker Hub...'
                withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                    sh '''
                        echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
                        docker push $IMAGE_NAME:$TAG
                    '''
                }
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deploying Docker container...'
                sh 'docker run -d -p 3000:3000 $IMAGE_NAME:$TAG'
            }
        }
    }
}
