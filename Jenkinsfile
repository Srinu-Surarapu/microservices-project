pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Docker-Cred', toolName: 'docker') {
                        sh "docker build -t srinusurarapu/frontend:S2 ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Docker-Cred', toolName: 'docker') {
                        sh "docker push srinusurarapu/frontend:S2"
                    }
                }
            }
        }
    }
}
