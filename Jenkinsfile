pipeline {
    agent { label 'jenkinslave' }
    stages {
        stage('Pull container image') {
            steps {
                sh "sudo chown root:jenkins /run/docker.sock"
                sh 'sudo docker pull maven:3-alpine'
            }
        }
        stage('Front-end') {
            agent {
                docker { image 'node:7-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
