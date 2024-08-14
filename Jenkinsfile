pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the project using Maven...'
                // Add your actual build commands here
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests using JUnit...'
                // Add your actual test commands here
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code using SonarQube...'
                // Add your actual code analysis commands here
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP Dependency-Check...'
                // Add your actual security scan commands here
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment on AWS EC2...'
                // Add your actual deployment commands here
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging using Selenium...'
                // Add your actual integration test commands here
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment on AWS EC2...'
                // Add your actual production deployment commands here
            }
        }
    }
    post {
        always {
            emailext(
                subject: "Jenkins Pipeline Notification - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
                    Hi Team,

                    The Jenkins pipeline for the job '${env.JOB_NAME}' build #${env.BUILD_NUMBER} has completed with the following status: ${currentBuild.currentResult}.

                    You can check the build details here: ${env.BUILD_URL}

                    Best regards,
                    Jenkins
                """,
                to: "manalgupta01012005@gmail.com",
                attachLog: true
            )
        }
    }
}
