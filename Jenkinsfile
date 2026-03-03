pipeline {
    agent none

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
                // Add your build steps here
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
