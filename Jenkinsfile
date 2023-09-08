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
                echo 'Test Automation Tools: Selenium'  
            }
            post {
                success {
                    mail to: 'sohanreddy58@gmail.com',
                    subject: 'Test Stage Success',
                    body: 'The test stage has passed successfully.',
                    attachLog: true
                }
                failure {
                    mail to: 'sohanreddy58@gmail.com',
                    subject: 'Test Stage Failure',
                    body: 'The test stage has failed.',
                    attachLog: true
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Your Code Analysis Tool Command'  
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Your Security Scan Tool Command'  
            }
            post {
                success {
                    mail to: 'sohanreddy58@gmail.com',
                    subject: 'Security Scan Stage Success',
                    body: 'The security scan stage has passed successfully.',
                    attachLog: true
                }
                failure {
                    mail to: 'sohanreddy58@gmail.com',
                    subject: 'Security Scan Stage Failure',
                    body: 'The security scan stage has failed.',
                    attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Your Deployment Command for Staging'  
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Your Integration Tests Command for Staging'  
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Your Deployment Command for Production'  
            }
        }
    }
}
