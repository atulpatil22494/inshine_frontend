pipeline {
    
    agent any 
        
    stages {
        
        stage('Checkout'){
           steps { 
                git credentialsId: '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',
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
                    '''
                }
            }
        }


    }
}
