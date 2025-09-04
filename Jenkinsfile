pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Running build steps..."
            }
        }
    }

    post {
        success {
            sh '''
              curl -X POST -H "Content-type: application/json" \
              --data "{\"text\":\"✅ Pipeline Job: ${JOB_NAME} Build #${BUILD_NUMBER} SUCCESS\"}" \
              https://hooks.slack.com/services/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
            '''
        }
        failure {
            sh '''
              curl -X POST -H "Content-type: application/json" \
              --data "{\"text\":\"❌ Pipeline Job: ${JOB_NAME} Build #${BUILD_NUMBER} FAILED\"}" \
              https://hooks.slack.com/services/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
            '''
        }
    }
}
