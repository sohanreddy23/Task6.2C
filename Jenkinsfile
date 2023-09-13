
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
                    emailext attachLog: true, body: 'The Unit and Integration Tests stage has passed successfully.', subject: 'Unit and Integration Stage Success', to: 'Sohanreddy58@gmail.com'
                }
                failure {
                   emailext attachLog: true, body: 'The Unit and Integration Tests stage has Failed.', subject: 'Unit and Integration Stage Failed', to: 'Sohanreddy58@gmail.com'
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
                    emailext attachLog: true, body: 'The security scan stage has passed successfully.', subject: 'Security Scan Stage Success', to: 'Sohanreddy58@gmail.com'
                    
                }
                failure {
                    emailext attachLog: true, body: 'The security scan stage has failed.', subject: 'Security Scan Stage fail', to: 'Sohanreddy58@gmail.com'
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
