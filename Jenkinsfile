
pipeline {
   agent any
   tools {
      nodejs "nodejs-20.x"
   }
   stages{
      stage('checkout') {
         steps {
            checkout scm
         }
      }
      stage('Install dependencies') {
         steps {

            sh 'node -v'
            // sh 'curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash'
            // sh '. ~/.nvm/nvm.sh'
            // sh 'nvm install 18'
            sh 'curl -f https://get.pnpm.io/v6.js | node - add --global pnpm '
            sh 'pnpm -v'
            sh 'pnpm install'
         }
      }
      stage('Build and run') {
         steps {
            sh 'pnpm run start'
         }
      }
   }
}
