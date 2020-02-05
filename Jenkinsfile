pipeline {
    agent any
    options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
    }
    stages {
        stage('--build--') {
            steps {
                sh "docker build -t omnipotentpenguin/starkeeper-dev-frontend ."
            }
        }
        stage('--push--') {
            steps {
                withDockerRegistry([ credentialsId: "dockerhub-adam", url: "" ]){
                    sh "docker push omnipotentpenguin/starkeeper-dev-frontend:latest"
                }
            }
        }        
    }
}
