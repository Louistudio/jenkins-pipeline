pipeline{
    agent any
    environment{
        AWS_REGION = 'us-east-1'
        ECR_REPO = ' 414935052400.dkr.ecr.us-east-1.amazonaws.com/jenkins-ci'
    }
    stages{
        stage('CodeScan'){
            steps{
                sh 'trivy fs . -o result.html'
                sh 'cat result.html'
            }
        }
        stage('dockerlogin'){
            steps{
                sh 'aws ecr get-login-password --region us-east-1 \
                | docker login --username \
                AWS --password-stdin 414935052400.dkr.ecr.us-east-1.amazonaws.com'
            }
        }
        stage('DockerImageBuild'){
            steps{
                sh 'docker build -t jenkins-ci .'
        }    
    }
        stage('imagetag'){
            steps{
                sh "docker tag jenkins-ci:latest \
                $ECR_REPO:latest"
            }
        }
        stage ('pushimage'){
            steps{
                sh "docker push $ECR_REPO:latest"
        }
    }

    }
}
