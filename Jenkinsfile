pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'g++ -c main/hello.cpp'
                sh 'g++ -o hello main/hello.cpp'
                echo 'build stage successfull'
            }
        }
        stage('Test'){
            steps{
                sh './hello'
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
