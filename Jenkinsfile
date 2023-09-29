pipeline {
    
    agent any 
        
    stages {      

        stage('Build Docker'){
            steps{
                script{
                    sh '''
                    echo 'Buid Docker Image'
                    docker build -t atulpatil22/jenkins_docker .
                 // docker run -dp 3000:3000 atulpatil22/jenkins_docker1
                    '''
                }

        stage('Build and Push Docker Image') {
             environment {
                DOCKER_IMAGE = "atulpatil22/jenkins_docker:${BUILD_NUMBER}"
             // DOCKERFILE_LOCATION = "java-maven-sonar-argocd-helm-k8s/spring-boot-app/Dockerfile"
                REGISTRY_CREDENTIALS = credentials('b28492e4-7cc1-4d25-b2ef-1456245c7fe0')
              }
            }
        }
    }
  }
}
