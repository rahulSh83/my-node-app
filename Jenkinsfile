pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'rahu01lsharma/my-node-app'
        DOCKERHUB_CREDENTIALS = 'd9976159-49b4-4269-aa50-a8898debdd95' // id of your DockerHub Credentials
    }

    stages {
        stage('Clone repository') {
            steps {
                git branch: 'main', url: 'https://github.com/rahulSh83/my-node-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(DOCKER_IMAGE)
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', DOCKERHUB_CREDENTIALS) {
                        docker.image(DOCKER_IMAGE).push('latest')
                    }
                }
            }
        }
    }
}
