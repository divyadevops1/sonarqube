@Library("my-shared-lib") _

pipeline {
    agent any

    stages {
        stage("Checkout") { 
            steps {
                echo "Code already checked out by Jenkins SCM"
            }
        }

        stage("Code Quality - SonarQube") {
            steps {
                withSonarQubeEnv('sonar-server') {
                    sh 'sonar-scanner'
                }
            }
        }

    }}
