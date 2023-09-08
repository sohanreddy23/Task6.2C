pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                    echo 'Build: Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Test Automation Tools : Seleniu'  
            }
            post {
                success {
                    mail to:'sohanreddy58@gmail.com'
                    subject: 'Test Stage Success',
                    body: 'The test stage has passed successfully.',
                    attachLog: true,
                }
                failure {
                   mail to:'sohanreddy58@gmail.com'
                    subject: 'Test Stage Success',
                    body: 'The test stage has passed successfully.',
                    attachLog: true,
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'your-analysis-tool-command'  
            }
        }
        stage('Security Scan') {
            steps {
                echo 'your-security-scan-tool-command'  
            }
            post {
                success {
                    mail to:'sohanreddy58@gmail.com'
                    subject: 'Test Stage Success',
                    body: 'The test stage has passed successfully.',
                    attachLog: true,
                }
                failure {
                    mail to:'sohanreddy58@gmail.com'
                    subject: 'Test Stage Success',
                    body: 'The test stage has passed successfully.',
                    attachLog: true,
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'your-deployment-command-for-staging'  
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'your-integration-tests-command-for-staging'  
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'your-deployment-command-for-production'  
            }
        }
    }
}
