pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the project using Maven...'
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
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP Dependency-Check...'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment on AWS EC2...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging using Selenium...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment on AWS EC2...'
            }
        }
    }
    post {
        always {
            // Send an aggregated test report via email using Test Results Aggregator
            emailext(
                subject: "Pipeline Notification - Build ${currentBuild.fullDisplayName}",
                body: """The pipeline for ${env.JOB_NAME} build ${currentBuild.fullDisplayName} has completed with the following status: ${currentBuild.currentResult}.

                Please find the attached test results.""",
                recipientProviders: [[$class: 'DevelopersRecipientProvider']],
                attachmentsPattern: '**/target/surefire-reports/*.xml'
            )
        }
    }
}
