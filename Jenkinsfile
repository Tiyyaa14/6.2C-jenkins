pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'echo "Build log contents" > build.log'  // Create a dummy build log
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
        always {
            script {
                sh 'cp ${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_NUMBER}/log build.log || echo "Log file not found"'
            }
        }
        
        success {
            emailext(
                subject: "Jenkins Pipeline Success",
                body: "The pipeline execution was successful.\n\nPlease find the build log attached.",
                to: "tiyakukar05@gmail.com",
                attachmentsPattern: "build.log"
            )
        }
        
        failure {
            emailext(
                subject: "Jenkins Pipeline Failed",
                body: "The pipeline execution failed.\n\nPlease find the build log attached.",
                to: "tiyakukar05@gmail.com",
                attachmentsPattern: "build.log"
            )
        }
    }
}
