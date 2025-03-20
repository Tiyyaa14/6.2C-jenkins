pipeline {
    agent any
    environment {
        EMAIL = 'simranpreetkaur23105@gmail.com'
    }
    triggers {
        githubPush() 
    }
    stages {
        stage('Build') {
            steps {
                echo 'Build stage: Build stage is running.'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Test stage: Simulating unit and integration tests...'
            }
            post {
                always {
                    emailext subject: "Test Stage Result: ${currentBuild.currentResult}",
                             to: "${env.EMAIL}",
                             attachLog: true,
                             body: "Test stage completed with status: ${currentBuild.currentResult}"
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Code Analysis stage: Simulating code quality analysis...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Security Scan stage: Simulating security scan...'
            }
            post {
                always {
                    emailext subject: "Security Scan Result: ${currentBuild.currentResult}",
                             to: "${env.EMAIL}",
                             attachLog: true,
                             body: "Security scan completed with status: ${currentBuild.currentResult}"
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploy to Staging stage: Simulating deployment to staging...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Integration Tests on Staging: Simulating integration tests...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy to Production: Simulating deployment to production...'
            }
        }
    }
}
