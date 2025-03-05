pipeline{
    agent any
    stages{
        stage('CodeScan'){
            steps{
                sh 'trivy --version'
                
            }
        }
        stage('DockerImageBuild'){
            steps{
                sh 'docker -v'
        }    
    }
        stage ('createfile'){
            steps{
                sh 'docker ps'
        }
    }

    }
}
