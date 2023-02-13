pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'ls *'
                sh 'g++ -c hello.cpp'
                sh 'g++ -o PES1UG20CS629 hello.cpp'
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
