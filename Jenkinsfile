pipeline{
    agent any
    stages{
        stage('clone'){
            steps{
                sh 'echo "clone"'
                sh 'uname -r'
            }
        }
        stage('test'){
            steps{
                sh 'echo "text"'
        }    
    }
        stage ('createfile'){
            steps{
                sh 'touch text-$BUILD_ID'
        }
    }

    }
}
