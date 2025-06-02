pipeline {
    agent {
        docker {
            image 'openjdk:17-jdk-slim'
            args '-v /var/run/docker.sock:/var/run/docker.sock'  // mount Docker socket for Docker commands
        }
    }
    stages {
        stage('Check Docker Agent with Java Image') {
            steps {
                echo 'Checking Docker version inside Java slim image...'
                sh 'docker version || echo "Docker command not available"'

                echo 'Running hello-world container as test...'
                sh 'docker run --rm hello-world || echo "Failed to run hello-world container"'
            }
        }
    }
}
