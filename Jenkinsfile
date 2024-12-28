pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Docker-cred', toolName: 'docker') {
                        sh "docker build -t srinusurarapu/loadgenerator:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Docker-cred', toolName: 'docker') {
                        sh "docker push srinusurarapu/loadgenerator:latest"
                    }
                }
            }
        }
    }
}
