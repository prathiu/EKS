  pipeline {
    agent {
      label 'docker'
    }

    stages {
        stage('Building the docker image') {
            steps {
                sh 'docker build -t test .'
            }
        }
        stage('Remove old docker images') {
             steps {
                 sh 'docker rmi -f test'
            }
        }
         stage('Running the docker container') {
            steps {
                  sh 'docker container rm --force fe'
                  sh 'docker run -dt -p 80:80 --name fe test'
            }
        }
    }
}
