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
        steps {
          //  withDockerRegistry([ credentialsId: "1db5f8f5-dc39-47a6-9431-0735c4f42afe", url: "iad.ocir.io" ]) {      
            //sh 'sudo docker push iad.ocir.io/abannang/project02/node:latest'
            //}
            withCredentials([usernamePassword(credentialsId: '1db5f8f5-dc39-47a6-9431-0735c4f42afe', passwordVariable: '5hMC_#y>tzy+:CZfwEEq', usernameVariable: "abannang/abhiram.annangi@oracle.com")]) {
            sh "sudo docker login -u ${env.usernameVariable} -p ${env.passwordVariable}"
            sh 'sudo docker push iad.ocir.io/abannang/project02/node:latest'
            
           }
         }      
    }
}
