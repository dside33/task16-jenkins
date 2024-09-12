pipeline {
    agent { label 'ubuntu' }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'checkout'
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
