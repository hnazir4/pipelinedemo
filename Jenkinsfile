pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            when {
                branch 'master'
            }
            steps {
                script {
                    app = docker.build("tap_sample")
                    
                }
            }
        }
        stage('Push Docker Image') {
            when {
                branch 'master'
            }
            steps {
                script {
                    docker.withRegistry("https://922722940372.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws_login") {
                        app.push("tap_sample")
                        app.push("latest")
                    }
                }
            }
        }
    }
}
