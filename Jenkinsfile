pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            
            steps {
                script {
                    app = docker.build("demo")
                    
                }
            }
        }
        stage('Push Docker Image') {
            
            steps {
                script {
                    docker.withRegistry("https://922722940372.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws_login") {
                        app.push("demo")
                        app.push("latest")
                    }
                }
            }
        }
    }
}

