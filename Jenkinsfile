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
                }
            }
        }
    }
}