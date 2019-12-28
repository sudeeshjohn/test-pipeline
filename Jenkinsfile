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
                    docker.withRegistry('', 'dockerhub') {
                        sh "docker push pensu/test:${BUILD_NUMBER}"
                    }
                }
            }
        }
    }
}
