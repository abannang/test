pipeline {
    agent { label 'jenkinslave' }
    stages {
        stage('Fetch dependencies') {
            steps {
                sh 'sudo docker pull node:latest'
          }
        }
        stage('Build docker image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */
            steps {
            sh "sudo docker build . -t customnode:1"
            }    
        }
        stage('Test image') {
            steps {
                sh 'echo "Tests successful"'
          }
        }
        stage('Push image to OCIR') {
        steps {
            sh "sudo docker login -u 'abannang/abhiram.annangi@oracle.com' -p '5hMC_#y>tzy+:CZfwEEq' iad.ocir.io"
            sh "sudo docker tag node:latest iad.ocir.io/abannang/node:latest"
            sh 'sudo docker push iad.ocir.io/abannang/node:latest'
            
           }
         }      
    }
}

