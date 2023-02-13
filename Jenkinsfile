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
                sh './PES1UG20CS629'
                echo 'test stage successful'
                post{
                    always{
                        junit 'target/surefire-reports/*.xml'
                    }
                }
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
