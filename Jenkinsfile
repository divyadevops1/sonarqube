Library("my-shared-lib") _
pipeline {
    agent any

    stages {
        stage("checkout") { 
        }
        stage("code quality sonar check") {
            steps {
                withSonarQubeEnv('My SonarQube Server') {
                    sh '''
                    sonar-scanner
                    '''
                }
                
                }
            }
        }
    }
