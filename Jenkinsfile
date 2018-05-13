pipeline {
    agent { label 'docker' }
    stages {
        stage('Pull container image') {
            sh 'sudo docker pull maven:3-alpine'
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
