pipeline {
    agent none

    parameters {
        string(name: 'NAME', defaultValue: 'default value', description: 'NAME PLZZ')
        booleanParam(name: 'SKIPTEST', description: 'This is a boolean parameter')
        choice(name: 'BARANCH', choices: ['TEST', 'STAGING', 'PRODUCTION'], description: 'This is a choice parameter')
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
                echo "Param1 value: ${params.NAME}"
                echo "Param2 value: ${params.SKIPTEST}"
                echo "Param3 value: ${params.BARANCH}"
                
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
