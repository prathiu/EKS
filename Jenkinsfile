 pipeline {
    agent {
      label 'docker'
    }

    stages {
      

        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image
                    def dockerImage = docker.build('my-html-page:latest', "-f Dockerfile .")

                    
                    
                }
            }
        }

        stage('Deploy Docker Container') {
            steps {
                // Run the Docker container
                sh 'docker run -d -p 80:80 my-html-page:latest'
            }
        }
    }

    post {
        success {
            // Perform any post-deployment actions here
            echo 'HTML page deployed successfully.'
        }
    }
}
