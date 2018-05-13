pipeline {
    agent { label 'jenkinslave' }
//    stages {
  //      stage('Pull container image') {
    //        steps {
                //sh "sudo chown root:jenkins /run/docker.sock"
                
                //sh 'sudo docker pull maven:3-alpine'
      //      }
        //}
        stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }
        stage('Front-end') {
            agent {
                docker { 
                    image 'node:7-alpine'
                     args ' -u root:sudo -v /var/lib/jenkins/workspace/test_master-YKUBYJHFWV5SAO5BKANKYXEX6RUGQUBB2GGZLHYPHNUKZELZPATQ:/test_master-YKUBYJHFWV5SAO5BKANKYXEX6RUGQUBB2GGZLHYPHNUKZELZPATQ'
                }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
