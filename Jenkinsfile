pipeline {
    agent any
    environment {
        CI = 'true'
        NODE_ENV = 'production'
        DOCKER_IMAGE = 'nextjs'
    }
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Gantilah perintah ini sesuai dengan nama Dockerfile Anda
                    sh 'docker build -t $DOCKER_IMAGE -f Dockerfile .'
                }
            }
        }

        stage('Deploy to Docker') {
            steps {
                script {
                    // Gantilah perintah ini sesuai dengan nama container dan konfigurasi deployment Anda
                    sh 'docker run -d --name nama-container-docker -p 3000:3000 $DOCKER_IMAGE'
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
