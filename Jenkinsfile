node {
    stage "SCM checkout"
        sh "rm -rf test-pipeline && git clone https://github.com/Pensu/test-pipeline"
    stage "Docker build"
        sh "cd test-pipeline"
        sh "docker build -t test ."
}
