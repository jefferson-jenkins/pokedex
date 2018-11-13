pipeline {
    agent any
    stages {
        stage('Check diff') {
            steps {
                checkout scm
                sh 'printenv'
            }
        }
        stage('Example') {
            steps {
                echo 'Hello World'
                echo ${env.BRANCH_NAME}
            }
        }
    }
}
