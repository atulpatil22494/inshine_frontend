    pipeline {
    
    agent any 
        
    stages {
        
       stage('Build and Push Docker Image') {
         environment {
           DOCKER_IMAGE = "atulpatil22/jenkins_docker:${BUILD_NUMBER}"    
           REGISTRY_CREDENTIALS = credentials('docker-cred')
        }
         steps {
           script {
               sh '''
                 docker build -t ${DOCKER_IMAGE} .
                 docker login -u atulpatil22 -p ${REGISTRY_CREDENTIALS}
                 docker push ${DOCKER_IMAGE}
                 '''

              }
           }
         }
      }
   }

       



