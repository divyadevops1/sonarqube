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
                    sh '''
                      sonar-scanner \
                      -Dsonar.projectKey=node_backend \
                      -Dsonar.projectName="Node Backend" \
                      -Dsonar.sources=.
                    '''
                }
            }
        }

        stage("Quality Gate") {
            steps {
                timeout(time: 1, unit: 'HOURS') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }
    }
}
