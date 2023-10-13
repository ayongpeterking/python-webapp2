pipeline {
    agent{
        label "docker-node"
    }

    stages {
        stage('Checkout') {
            steps {
                // This step pulls the code from the configured Git repository in Jenkins job configuration.
                checkout scm
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    // Authenticate with Docker Hub using the specified credentials
                    docker.withRegistry('https://registry.hub.docker.com/', 'dockerhub-credentials') {
                        // Build the Docker image
                        def appImage = docker.build("donpk/py-webapp:${env.BUILD_ID}")

                        // Push the image to Docker Hub
                        appImage.push()

                        // Tag the same image as 'latest'
                        appImage.push('latest')
    }
}
            }
        }
    }
}
