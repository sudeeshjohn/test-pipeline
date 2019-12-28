pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh "docker build -t test:${BUILD_NUMBER} ."
            }
        }
        stage('Push') {
                docker.withRegistry('https://hub.docker.com', 'dockerhub') {
                    sh "docker login -u ${USERNAME} -p ${PASSWORD}"
                    sh "docker push test:${BUILD_NUMBER}"
                }
        }
    }
}
