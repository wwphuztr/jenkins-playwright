pipeline {
   agent { docker { 
      image 'mcr.microsoft.com/playwright:v1.44.1-jammy'
      args '-u root:root'
      } 
   }
   stages {
      stage('e2e-tests') {
         steps {
            sh 'npm install -g npm@latest'
            sh 'npm cache clean --force'
            sh 'mkdir -p /.npm && chown -R 987:981 /.npm'
            sh 'npm ci'
            sh 'npx playwright test'
         }
      }
   }
}
