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
                sh './main/hello'
                echo 'test stage successful'
            }
        }
        stage('Deploy'){
            steps{
                sh 'mvn deploy'
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
