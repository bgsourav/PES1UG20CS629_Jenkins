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
