pipeline {
    agent any

    stages {
        stage('Build Image') {
            steps {
                docker.build('tap_sample')
            }
        }
        stage('Push Image') {
            steps {
                docker.withRegistry("https://922722940372.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws_login") 
                    docker.image('tap_sample').push('latest')
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
