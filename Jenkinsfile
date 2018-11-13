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
      when {
        branch 'feature/*'
      }
      steps {
        echo 'Feature steps only'
      }
    }
    stage('Example') {
      parallel {
        stage('Example') {
          steps {
            echo 'Hello World'
            echo "${env.BRANCH_NAME}"
          }
        }
        stage('Upload to HockeyApp') {
          steps {
            echo 'Uploading to Hockeyapp'
          }
        }
      }
    }
    stage('Finish') {
      parallel {
        stage('Finish') {
          steps {
            echo 'Finish'
          }
        }
        stage('Test') {
          steps {
            echo 'Test'
          }
        }
      }
    }
  }
}