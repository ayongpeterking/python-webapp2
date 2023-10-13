pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // This step pulls the code from the configured Git repository in Jenkins job configuration.
                checkout scm
            }
        }
        // You can add additional stages for build, test, deploy, etc.
    }
}
