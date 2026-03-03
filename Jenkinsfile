pipeline {
    agent { label 'slave1' }

    stages {
        stage('stage 1') {
            steps {
                echo 'this is stage 1'
                // Add your build steps here
            }
        }
        stage('stage 2') {
            steps {
                echo 'this is stage 2'
                // Add your build steps here
            }
        }
        stage('stage 3') {
            steps {
                echo 'this is stage 3'

                sh 'ls -l'

            }
        }
        stage('stage 4') {
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
