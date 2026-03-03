pipeline {
    agent none

    parameters {
        string(name: 'PARAM1', defaultValue: 'default value', description: 'This is a string parameter')
        booleanParam(name: 'PARAM2', defaultValue: true, description: 'This is a boolean parameter')
        choice(name: 'PARAM3', choices: ['Option 1', 'Option 2', 'Option 3'], description: 'This is a choice parameter')
    }

    stages {
        stage('stage 1') {
            agent {label 'slave1'}
            steps {
                echo 'this is stage 1'

                sh '''
                sleep 10

                '''
            }
        }
        stage('stage 2') {
            agent {label 'slave1'}

            steps {
                echo 'this is stage 2'
                echo "Param1 value: ${params.PARAM1}"
                echo "Param2 value: ${params.PARAM2}"
                echo "Param3 value: ${params.PARAM3}"
                
            }
        }
        stage('stage 3') {
            agent {label 'slave2'}
            steps {
                echo 'this is stage 3'

                sh 'ls -l'

            }
        }
        stage('stage 4') {
            agent {label 'slave2'}
            steps {
                echo 'this is stage sds'

                
                sh '''
                #!/bin/bash
                echo "Running multiple commands in stage 4"
                ls -lrt
                echo "Finished listing files"
                sleep 10
                '''
            }
        }
    }
}
