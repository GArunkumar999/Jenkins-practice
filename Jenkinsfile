pipeline{
    agent { label 'AGENT-1' }
    environment{
        project="expense"
        component="backend"
    }
    stages{
        stage('build'){
            steps{
                script{
                    echo "This is build"
                    echo "project is ${project}"
                    echo "component is ${component}"
                }
            }
        }
        stage('test'){
            steps{
                script{
                    echo "This is test"
                }
            }
        }
        stage('deploy'){
            steps{
                script{
                    echo "This is deploy"
                }
            }
        }
    }
    post{
        always{
            echo "say hello always"
            deleteDir()
        }
        success{
            echo "say hello in success"
        }
        failure{
            echo "say hello in failure"
        }
        unsuccessful{
            echo "say hello in unsuccessful"
        }
    }
}