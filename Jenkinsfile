    pipeline {
    
    agent any 
        
    stages {
        
       stage('Build and Push Docker Image') {
         environment {
           DOCKER_IMAGE = "atulpatil22/jenkins_docker:${BUILD_NUMBER}"    
           REGISTRY_CREDENTIALS = credentials('b28492e4-7cc1-4d25-b2ef-1456245c7fe0')
        }
         steps {
           script {
               sh 'docker build -t ${DOCKER_IMAGE} .'
               def dockerImage = docker.image("${DOCKER_IMAGE}")
               docker.withRegistry('https://index.docker.io/v1/', "b28492e4-7cc1-4d25-b2ef-1456245c7fe0") {
                   dockerImage.push()
              }
           }
         }
      }
   }
}
       



