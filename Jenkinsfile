pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('Check diff') {
            steps {
                checkout(
                    [
                        $class: 'GitSCM', 
                        branches: [
                            [name: '*/master'], 
                            [name: 'origin/features/*']
                        ], 
                        doGenerateSubmoduleConfigurations: false, 
                        extensions: [], 
                        submoduleCfg: [], 
                        userRemoteConfigs: [[url: 'git@github.com:jeffersonsetiawan/pokedex.git']]
                    ]
                )
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
