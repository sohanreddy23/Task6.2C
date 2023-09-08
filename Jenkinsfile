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
                    emailext(
                        to: 'sohanreddy58@gmail.com',
                        subject: 'Test Stage Success',
                        body: 'The test stage has passed successfully.',
                        attachmentsPattern: '**/*.log'
                    )
                }
                failure {
                    archiveArtifacts artifacts: '**/*.log', allowEmptyArchive: true
                    emailext(
                        to: 'sohanreddy58@gmail.com',
                        subject: 'Test Stage Failure',
                        body: 'The test stage has failed.',
                        attachmentsPattern: '**/*.log'
                    )
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
                    archiveArtifacts artifacts: '**/*.log', allowEmptyArchive: true
                    emailext(
                        to: 'sohanreddy58@gmail.com',
                        subject: 'Security Scan Stage Success',
                        body: 'The security scan stage has passed successfully.',
                        attachmentsPattern: '**/*.log'
                    )
                }
                failure {
                    archiveArtifacts artifacts: '**/*.log', allowEmptyArchive: true
                    emailext(
                        to: 'sohanreddy58@gmail.com',
                        subject: 'Security Scan Stage Failure',
                        body: 'The security scan stage has failed.',
                        attachmentsPattern: '**/*.log'
                    )
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

