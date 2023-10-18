pipeline {
    agent{
       label 'docker'
    }

   

    stages {
        
        
        stage('Building the docker image') {
            steps {
                sh 'docker build -t prathiusha/practice1  .'
            }
        }
        
        
         stage('Running the docker container') {
            steps {
                  sh 'docker container rm --force container'
                  sh 'docker run -d -p 80:80 --name container prathiusha/practice1 '
            }
        }
    }
}
