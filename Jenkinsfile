post {
    success {
        sh '''
          curl -X POST -H "Content-type: application/json" \
          --data "{\"text\":\"✅ Pipeline Job: slackp Build #${BUILD_NUMBER} SUCCESS\"}" \
          https://hooks.slack.com/services/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
        '''
    }
}
