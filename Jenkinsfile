pipeline {
    agent { label 'jenkinslave' }
    stages {
        stage('Pull maven image') {
            steps {
                sh 'sudo docker pull maven:3-alpine'
            }
        }
        stage('pull node image') {
            steps {
                sh 'sudo docker pull node:latest'
          }
        }
        stage('push images') {
        withDockerRegistry([ credentialsId: "1db5f8f5-dc39-47a6-9431-0735c4f42afe", url: "iad.ocir.io" ]) {
                sh 'sudo docker push iad.ocir.io/abannang/project02/node:latest'
           }
         }      
    }
}
