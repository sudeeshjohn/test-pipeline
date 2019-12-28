pipeline {
    agent any
    
    stages {
        stage ('Clone the repo') {
            steps {
                sh "rm -rf test-pipeline && git clone https://github.com/Pensu/test-pipeline"
            }
        }
        stage('Build') {
            steps {
                sh "cd test-pipeline && docker build -t pensu/test:${BUILD_NUMBER} ."
            }
        }
        stage('Test') {
            steps {
                sh "docker run pensu/test:${BUILD_NUMBER}"
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
