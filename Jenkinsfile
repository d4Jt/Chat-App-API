pipeline {
   agent any
   stages{
      stage('checkout') {
         steps {
            checkout scm
         }
      }
      // stage('Git clone') {
      //    steps {
      //       git 'https://github.com/d4Jt/Chat-App-API.git'
      //    }
      // }
       stage('Login docker') {
          steps {
            sh 'docker login -u $USERNAME -p $PASSWORD'
          }
       }

       stage('Docker build and push') {
          steps {
             sh 'docker build -t $USERNAME/chat-app:1.0 .'
             sh 'docker push $USERNAME/chat-app:1.0'
             sh 'docker run -dp 4090:4090 $USERNAME/chat-app:1.0
             sh 'docker logout'
            //  withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
            //     sh 'docker login -u $USERNAME -p $PASSWORD'
            //     sh 'docker tag chat-app:1.0 $USERNAME/chat-app:1.0'
            //     sh 'docker push $USERNAME/chat-app:1.0'
            //     sh 'docker logout'
            //  }

          }
       }
   }
}
