pipeline {
    agent {
        label 'docker'
    }

    stages {
        stage ('Build docker image') {
            steps {
                script {

                    sh 'docker build -t moatazmkhaled/docker-react -f Dockerfile.dev .'
                }
            }
        }
        stage ('Run test') {
            steps {
                script {
                    env.DOCKERBUILDKIT = 1
                    sh 'docker run -e CI=true moatazmkhaled/docker-react npm test'
                }
            }
        }
    }

}