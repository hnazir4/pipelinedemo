pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                docker build -t tap_sample .
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
