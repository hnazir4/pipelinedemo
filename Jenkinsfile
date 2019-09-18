pipeline {
    agent any

    stages {
        stage('Build Image') {
            steps {
                app = docker.build("tap_sample")
            }
        }
        stage('Push Image') {
            steps {
                docker.withRegistry("https://922722940372.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws_login") {
                    app.push("tap_sample")
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
