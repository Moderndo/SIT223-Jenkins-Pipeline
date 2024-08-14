pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clones the GitHub repository to the Jenkins workspace
                git branch: 'main', url: 'https://github.com/YourUsername/YourRepository.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                // Add your build commands here, e.g., compiling code
            }
        }

        stage('Unit Tests') {
            steps {
                echo 'Running unit tests...'
                // Add your testing commands here
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with SonarQube...'
                // Add your code analysis commands here
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Add your security scan commands here
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                // Add your staging deployment commands here
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                // Add your production deployment commands here
            }
        }
    }

    post {
        always {
            emailext(
                subject: "Jenkins Build - ${env.JOB_NAME} #${env.BUILD_NUMBER} - ${currentBuild.currentResult}",
                body: """
                    Hi Team,

                    The Jenkins build for the job '${env.JOB_NAME}' (build #${env.BUILD_NUMBER}) has completed with status: ${currentBuild.currentResult}.

                    Check the details here: ${env.BUILD_URL}

                    Best regards,
                    Jenkins
                """,
                to: 'manalgupta01012005@gmail.com',
                attachLog: true
            )
        }
    }
}
