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
              curl -X POST -H 'Content-type: application/json' \
              --data '{"text":"✅ Pipeline Job: ${JOB_NAME} Build #${BUILD_NUMBER} SUCCESS"}' \
              https://hooks.slack.com/services/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
            '''
        }
        failure {
            sh '''
              curl -X POST -H 'Content-type: application/json' \
              --data '{"text":"❌ Pipeline Job: ${JOB_NAME} Build #${BUILD_NUMBER} FAILED"}' \
              https://hooks.slack.com/services/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
            '''
        }
    }
}
