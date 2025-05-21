pipeline{
    agent { label 'AGENT-1' }
    environment{
        project="expense"
        component="backend"
    }
    options { 
        retry(3)
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        }
    // parameters {
    //     string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

    //     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

    //     booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

    //     choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

    //     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    // }
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
        stage('parameterstest'){
            steps{
                script{
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
                }
            }
        }
        stage('deploy'){
                input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
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