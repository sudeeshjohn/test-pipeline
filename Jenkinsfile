pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh "docker build -t test:${BUILD_NUMBER} ."
            }
        }
    }
}
