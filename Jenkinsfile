pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'g++ -c main/PES1UG20CS629.cpp'
                sh 'g++ -o PES1UG20CS629 main/PES1UG20CS629.cpp'
                echo 'build stage successfull'
            }
        }
        stage('Test'){
            steps{
                sh './PES1UG20CS629'
                echo 'test stage successful'
            }
        }
        stage('Deploy'){
            steps{
                sh "scp hello user@deploymentserver:/path/to/deployment/directory"
                sh "ssh user@deploymentserver 'cd /path/to/deployment/directory && ./hello restart'"
                echo 'Deployment Successful'
            }
        }
    }
    post{
        failure{
            echo 'Pipeline Failed'
        }
    }
}
