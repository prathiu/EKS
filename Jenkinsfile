 pipeline {
    agent{
       label 'docker'
    }

    environment {

    DOCKERHUB_CREDENTIALS = credentials('dockeruser')
     registry = "prathiusha/prathiusha1"
        registryCredential = 'dockeruser'
        dockerImage = ''
    }

    stages {
        
        
        stage('Building the docker image') {
            steps {
                sh 'docker build -t  prathiusha/prathiusha1 .'
            }
        }
        stage('Logging into dockerhub account') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('pushing the docker image into dockerhub') {
            steps {
                  sh 'docker push  prathiusha/prathiusha1'
            }
        }
        stage('Remove old docker images') {
             steps {
                 sh 'docker rmi -f  prathiusha/prathiusha1'
            }
        }
        
         stage('Running the docker container') {
            steps {
                  sh 'docker container rm --force container'
                  sh 'docker run -d -p 80:80 --name container prathiusha/prathiusha1'
            }
        }
    }
}
