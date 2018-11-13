pipeline {
    agent any
    stages {
        stage('Check diff') {
            steps {
                checkout scm
                sh 'printenv'
            }
        }
        stage('Feature') {
            when { branch "feature/*" }
            steps {
                echo 'Feature steps only'
            }
        }
        stage('Example') {
            steps {
                echo 'Hello World'
                echo "${env.BRANCH_NAME}"
            }
        }
    }
}
