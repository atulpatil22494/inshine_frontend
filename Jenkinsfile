pipeline {
    
    agent any 
        
    stages {
        

        stage('Build Docker'){
            steps{
                script{
                    sh '''
                    echo 'Buid Docker Image'
                    docker build -t atulpatil22/jenkins_docker1 .
                    docker run -dp 3000:3000 atulpatil22/jenkins_docker1
                    '''
                }
            }
        }


    }
}
