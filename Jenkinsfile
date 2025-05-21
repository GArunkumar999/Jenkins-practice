pipeline{
    agent { label 'AGENT-1' }
    stages{
        stage('build'){
            steps{
                script{
                    echo "This is build"
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
                    xftr
                }
            }
        }
    }
    post{
        always{
            echo "say hello always"
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