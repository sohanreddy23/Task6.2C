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
                    script {
                        emailext body: 'The test stage has passed successfully.',
                            subject: 'Test Stage Success',
                            to: 'sohanreddy58@gmail.com',
                            mimeType: 'text/plain',
                            attachLog: true
                    }
                }
                failure {
                    archiveArtifacts artifacts: '**/*.log', allowEmptyArchive: true
                    script {
                        emailext body: 'The test stage has failed.',
                            subject: 'Test Stage Failure',
                            to: 'sohanreddy58@gmail.com',
                            mimeType: 'text/plain',
                            attachLog: true
                    }
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
                    script {
                        emailext body: 'The security scan stage has passed successfully.',
                            subject: 'Security Scan Stage Success',
                            to: 'sohanreddy58@gmail.com',
                            mimeType: 'text/plain',
                            attachLog: true
                    }
                }
                failure {
                    archiveArtifacts artifacts: '**/*.log', allowEmptyArchive: true
                    script {
                        emailext body: 'The security scan stage has failed.',
                            subject: 'Security Scan Stage Failure',
                            to: 'sohanreddy58@gmail.com',
                            mimeType: 'text/plain',
                            attachLog: true
                    }
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
