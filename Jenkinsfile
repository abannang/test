pipeline {
    agent { label 'k8s' }
    stages {
        stage('Fetch dependencies') {
        /* This stage pulls the latest node image from
           Dockerhub */
            steps {
                sh 'sudo docker pull nginx:latest'
          }
        }
        stage('Build docker image') {
        /* This stage builds the actual image; synonymous to
           docker build on the command line */
            steps {
            sh "sudo docker build . -t customnginx:1"
            }    
        }
        stage('Test image') {
         /* This stage runs unit tests on the image; we are
            just running dummy test here */
            steps {
                sh 'echo "Tests successful"'
          }
        }
        stage('Push image to OCIR') {
         /* Final stage of build; Push the 
            docker image to our private Registry*/
        steps {
            sh "sudo docker login -u 'abannang/abhiram.annangi@oracle.com' -p '5hMC_#y>tzy+:CZfwEEq' iad.ocir.io"
            sh "sudo docker tag customnginx:1 iad.ocir.io/abannang/nginx:custom"
            sh 'sudo docker push iad.ocir.io/abannang/nginx:custom'
            
           }
         }      
    }
}

