pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            when {
                branch 'master'
            }
            steps {
                script {
                    app = docker.build("demo")
                    
                }
            }
        }
        stage('Push Docker Image') {
            when {
                branch 'master'
            }
            steps {
                script {
                    docker.withRegistry("532819289301.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws_login") {
                        app.push("demo")
                        app.push("latest")
                    }
                }
            }
        }
    }
}
