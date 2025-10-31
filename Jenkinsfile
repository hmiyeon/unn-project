node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("unn-project/mynginx0904")
         
     }
     stage('Push image') {
         docker.withRegistry('https://ec2-54-180-107-110.ap-northeast-2.compute.amazonaws.com/', 'harbor-reg12') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
