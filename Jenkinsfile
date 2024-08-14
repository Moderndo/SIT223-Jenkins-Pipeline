pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the project using Maven...'
            }
        }
        // Add other stages here...
    }
    post {
        always {
            emailext(
                subject: "Jenkins Build - ${env.JOB_NAME} #${env.BUILD_NUMBER} - ${currentBuild.currentResult}",
                body: "The build ${env.BUILD_NUMBER} for job ${env.JOB_NAME} has finished with status ${currentBuild.currentResult}.",
                to: "hashnagupta@gmail.com"
            )
        }
    }
}
