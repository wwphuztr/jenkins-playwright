pipeline {
   agent { docker { image 'mcr.microsoft.com/playwright:v1.44.1-jammy' } }
   stages {
      stage('e2e-tests') {
         steps {
            sh 'npm ci'
            sh 'npx playwright test'
         }
      }
   }
}