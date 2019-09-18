pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                docker.build('demo')
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
