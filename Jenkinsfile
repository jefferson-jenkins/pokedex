pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('Check diff') {
            steps {
                sh 'printenv'
            }
        }
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
