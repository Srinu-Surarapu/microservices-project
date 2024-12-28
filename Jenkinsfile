pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {

                    withDockerRegistry(credentialsId: 'Docker-cred', toolName: 'docker') {
                        sh "docker build -t srinusurarapu/cartservice:latest ."
                    }
                        }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Docker-cred', toolName: 'docker') {
                        sh "docker push srinusurarapu/cartservice:latest"
                    }
                }
            }
        }
    }
}
