pipeline {
    agent { label 'ubuntu' }

    environment {
        DOCKER_REGISTRY = "1side"
        DOCKER_IMAGE = "nginx-jenkins"
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
                sh "docker build -t ${DOCKER_REGISTRY}/${DOCKER_IMAGE}:14 -f Dockerfile.nginx ."
                echo 'FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF'
            }
        }
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World add lol'
            }
        }
    }
}
