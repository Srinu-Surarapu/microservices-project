pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Docker-Cred', toolName: 'docker') {
                        sh "docker build -t surarapusrinu/paymentservice:S2 ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Docker-Cred', toolName: 'docker') {
                        sh "docker push surarapusrinu/paymentservice:S2"
                    }
                }
            }
        }
    }
}
