pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clone the GitHub repository
                git branch: 'main', url: 'https://github.com/Moderndo/SIT223-Jenkins-Pipeline.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project using Maven...'
               
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests using JUnit...'
                // Add your test commands here
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
