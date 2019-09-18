pipeline {
    agent any
    
    stages {
        
        stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */

        app = docker.build("tap_sample")
        }
        
        stage('Push image') {
        /* Finally, we'll push the image with two tags:
         * First, the incremental build number from Jenkins
         * Second, the 'latest' tag.
         * Pushing multiple tags is cheap, as all the layers are reused. */

        docker.withRegistry("https://922722940372.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws_login") {
            app.push("tap_sample")
            
        }
    }
}
