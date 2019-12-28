node {
    stage "SCM checkout"
        sh "git clone --depth=1 https://github.com/Pensu/test-pipeline"
    stage "Docker build"
        sh "test-pipeline"
        sh "docker build -t test -f Dockerfile ."
}
