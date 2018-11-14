pipeline {
  agent any
  environment {
    HOCKEY_API_TOKEN_ENV = credentials('HOCKEY_API_TOKENZZZZ')
  }
  stages {
    stage('Check diff') {
      steps {
        checkout scm
        sh 'printenv'
        sh 'echo $HOCKEY_API_TOKEN_ENV'
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
      steps {
        echo 'Finish'
      }
    }
  }
}
