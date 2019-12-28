node {
    stage "SCM checkout"
        sh "git clone https://github.com/Pensu/test-pipeline"
    stage "Docker build"
        sh "docker build -t test -f Dockerfile ."
}
