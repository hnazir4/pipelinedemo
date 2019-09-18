pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                docker.build('tap_sample')
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
