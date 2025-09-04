@Library("my-shared-lib") _
pipeline {
    agent any

    stages {
        stage("Checkout") { 
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
