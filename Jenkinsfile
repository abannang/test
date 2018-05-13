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
                sh 'sudo docker pull maven:3-alpine'
          }
        }
        stage('build images') {
            steps {
                sh 'sudo docker build .'
          }
        }
    }
}
