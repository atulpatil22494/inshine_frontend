pipeline {
    
    agent any 
        
    stages {
        
        stage('Checkout'){
           steps { 
                url: 'https://github.com/atulpatil22494/inshine_frontend',
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
        }


    }
}
