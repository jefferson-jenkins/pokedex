pipeline {
  agent any
  environment {
    DEVELOPER_DIR = '/Applications/Xcode.app/Contents/Developer'
    KEYCHAIN_NAME = credentials('KEYCHAIN_NAME')
    KEYCHAIN_PASSWORD = credentials('KEYCHAIN_PASSWORD')
    MATCH_PASSWORD = credentials('MATCH_PASSWORD')
    FASTLANE_PASSWORD = credentials('FASTLANE_PASSWORD')
    HOCKEY_API_TOKEN = credentials('HOCKEY_API_TOKEN')
    FASTLANE_EXPLICIT_OPEN_SIMULATOR = 2
  }
  stages {
    stage('Print Env') {
      steps {
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
      steps {
        echo 'Finish'
      }
    }
  }
}
