node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("dlgndud/flask-example")
         
     }
     stage('Push image') {
         docker.withRegistry('https://hub.docker.com', 'docker-hub') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
