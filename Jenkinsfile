pipeline {
  agent any
  stages(
    stage("checkout") {
      steps {
        checkout scm
      }
    }
    stage("Test") {
      steps {
        sh 'sudo pnpm install'
        sh 'pnpm test'
      }
    }
    stage("Build) {
          steps {
            sh 'pnpm run start'
          }
    }
  )
}
