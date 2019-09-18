pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            
            steps {
                script {
                    app = docker.build("demo_1")
                    
                }
            }
        }
        stage('Push Docker Image') {
            
            steps {
                script {
                    docker.withRegistry("https://532819289301.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws_login") {
                        app.push("demo_1")
                        app.push("latest")
                    }
                }
            }
        }
    }
}

