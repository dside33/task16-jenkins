pipeline {
    agent { label 'ubuntu' }

    environment {
        DOCKER_REGISTRY = "1side"
        DOCKER_IMAGE = "nginx-jenkins"
        DOCKERHUB_CREDENTIALS = credentials('1side-dockerhub')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'checkout'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t ${DOCKER_REGISTRY}/${DOCKER_IMAGE}:${env.BUILD_NUMBER} -f Dockerfile.nginx ."
                echo 'Docker image built successfully'
            }
        }

        stage('Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        
        stage('Push') {
            steps {
                sh 'docker push ${DOCKER_REGISTRY}/${DOCKER_IMAGE}:${env.BUILD_NUMBER}'
            }
        }

        stage('Hello') {
            steps {
                echo 'Hello World add lol'
            }
        }
    }
}
