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
                    mail to: 'sohanreddy58@gmail.com',
                    subject: 'Test Stage Success',
                    body: 'The test stage has passed successfully.',
                    mimeType: 'text/plain'
                }
                failure {
                    mail to: 'sohanreddy58@gmail.com',
                    subject: 'Test Stage Failure',
                    body: 'The test stage has failed.'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Code Analysis Tool: SonarQube'  
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Security Scan Tool: Nessus'  
            }
            post {
                success {
                    mail to: 'sohanreddy58@gmail.com',
                    subject: 'Security Scan Stage Success',
                    body: 'The security scan stage has passed successfully.'
                    
                }
                failure {
                    mail to: 'sohanreddy58@gmail.com',
                    subject: 'Security Scan Stage Failure',
                    body: 'The security scan stage has failed.'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Staging Server: AWS EC2 instance'  
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Your Integration Tests for Staging: Selenium'  
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Production Server: AWS EC2 instance'  
            }
        }
    }
}
