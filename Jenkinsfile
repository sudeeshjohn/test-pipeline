pipeline {
    agent {
        node {
            label 'ppc64le-ubuntu'
        }
    }
    
    stages {
        stage('Build') {
            steps {
                sh "docker build -t sudheeshjohn/test:${BUILD_NUMBER} ."
            }
        }
        stage('Test') {
            steps {
                sh "docker run sudheeshjohn/test:${BUILD_NUMBER}"
            }
        }
        stage('Push') {
            steps {
                script {
                    docker.withRegistry('', 'dockerhub') {
                        sh "docker push sudheeshjohn/test:${BUILD_NUMBER}"
                    }
                }
            }
        }
    }
}
