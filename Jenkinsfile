pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Running security scan...'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging environment...'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on Staging...'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production environment...'
            }
        }
    }

    post {
        success {
            emailext(
                subject: "Jenkins Pipeline Success",
                body: "The pipeline execution was successful.",
                to: "tiyakukar05@gmail.com"
            )
        }
        
        failure {
            emailext(
                subject: "Jenkins Pipeline Failed",
                body: "The pipeline execution failed.",
                to: "tiyakukar05@gmail.com"
            )
        }
    }
}
