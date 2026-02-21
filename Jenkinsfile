stage("OWASP: Dependency check") {
    steps {
        sh '''
            mkdir -p reports/owasp
            docker run --rm -v $PWD:/app owasp/dependency-check:latest \
              --project "wanderlust" --scan /app --format "ALL" --out /app/reports/owasp
        '''
        archiveArtifacts artifacts: 'reports/owasp/*', allowEmptyArchive: true
    }
}
