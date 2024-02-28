pipeline {
  agent any
  stages(
    stage("checkout") {
      steps {
        checkout scm
      }
    }
    stage("test") {
      steps {
        sh 'curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash'
        sh '. ~/.nvm/nvm.sh'
        sh 'nvm install 18'
        sh 'curl -fsSL https://get.pnpm.io/install.sh | sh -'
        sh 'source /root/.bashrc'
        sh 'pnpm test'
      }
    }
    stage("build) {
          steps {
            sh 'pnpm run start'
          }
    }
  )
}
