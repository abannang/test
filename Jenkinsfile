pipeline {
    agent { label 'jenkinslave' }
    stages {
        stage('Pull container image') {
            steps {
                sh 'sudo docker pull maven:3-alpine'
            }
        }
        stage('build node') {
            agent {
                docker { image 'node:7-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
