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
                withSonarQubeEnv('sonar_server') {
                    sh 'sonar-scanner'
                }
            }
        }

    }}
