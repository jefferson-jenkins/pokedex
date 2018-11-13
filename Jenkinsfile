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
                echo branch
                echo 'Hello World'
                echo "${env.BRANCH_NAME}"
            }
        }
    }
}
