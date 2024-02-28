
pipeline {
   agent any
   stages{
      stage('checkout') {
         steps {
            checkout scm
         }
      }
      stage('Test') {
         steps {
            sh '''
            curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -
            yum install -y nodejs
            '''
            sh 'node -v'
            // sh 'curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash'
            // sh '. ~/.nvm/nvm.sh'
            // sh 'nvm install 18'
            sh 'curl -f https://get.pnpm.io/v6.js | node - add --global pnpm '
            sh 'pnpm -v'
            sh 'pnpm test'
         }
      }
      stage('Build') {
         steps {
            sh 'pnpm run start'
         }
      }
   }
}
