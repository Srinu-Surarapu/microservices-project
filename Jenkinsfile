pipeline { 
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Docker-cred', toolName: 'docker') {
                        sh "docker build -t srinusurarapu/shippingservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Docker-cred', toolName: 'docker') {
                        sh "docker push srinusurarapu/shippingservice:latest"
                    }
                }
            }
        }
    }
}
