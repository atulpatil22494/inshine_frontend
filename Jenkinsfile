pipeline {
    
    agent any 
        
    stages {
        
        stage('Checkout'){
           steps {
                git credentialsId: '57adf257-3c13-4da7-9068-59675d3f7a62', 
                url: 'https://github.com/iam-veeramalla/cicd-end-to-end',
                branch: 'main'
           }
        }

        stage('Build Docker'){
            steps{
                script{
                    sh '''
                    echo 'Buid Docker Image'
                    docker build -t atulpatil22/jenkins_docker .
                    docker run -dp 3000:3000 atulpatil22/jenkins_docker
                    '''
                }
            }
            
    pipeline {
    
    agent any 
        
    stages {
        
        stage('Checkout'){
           steps {
                git credentialsId: '57adf257-3c13-4da7-9068-59675d3f7a62', 
                url: 'https://github.com/iam-veeramalla/cicd-end-to-end',
                branch: 'main'
           }
        }

        stage('Build Docker'){
            steps{
                script{
                    sh '''
                    echo 'Buid Docker Image'
                  //  docker build -t atulpatil22/jenkins_docker .
                  //  docker run -dp 3000:3000 atulpatil22/jenkins_docker
                    '''
                }
            }
            
     stage('Build and Push Docker Image') {
      environment {
        DOCKER_IMAGE = "atulpatil22/jenkins_docker:${BUILD_NUMBER}"
        // DOCKERFILE_LOCATION = "java-maven-sonar-argocd-helm-k8s/spring-boot-app/Dockerfile"
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
}
        }


    }
}
