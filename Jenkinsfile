pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Build Automation Tool: Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Test Automation Tools: Selenium'  
            }
            post {
                success {
                    archiveArtifacts artifacts: '**/*.log', allowEmptyArchive: true
                    emailext (
                        to: 'sohanreddy58@gmail.com',
                        subject: 'Test Stage Success',
                        body: 'The test stage has passed successfully.',
                        attachLog: true
                    )
                }
                failure {
                    archiveArtifacts artifacts: '**/*.log', allowEmptyArchive: true
                    emailext (
                        to: 'sohanreddy58@gmail.com',
                        subject: 'Test Stage Failure',
                        body: 'The test stage has failed.',
                        attachLog: true
                    )
                }
            }
        }
        // ... (other stages)
    }
}
