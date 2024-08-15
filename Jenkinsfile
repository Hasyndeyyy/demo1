pipeline {
    agent any
    
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Hasyndeyyy/demo1.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'demo-hub1', url: 'https://index.docker.io/v1/') {
                        // Build Docker image
                        sh 'docker build -t danphuong/nginx .'
                        // Push Docker image to Docker Hub
                        sh 'docker push danphuong/nginx'
                    }
                }
            }
        }
    }
}
