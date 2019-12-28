pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh "docker build -t pensu/test:${BUILD_NUMBER} ."
            }
        }
        stage('Push') {
            steps {
                script {
                    docker.withRegistry('https://hub.docker.com', 'dockerhub') {
                        dockerImage.Push()
                    }
                }
            }
        }
    }
}
