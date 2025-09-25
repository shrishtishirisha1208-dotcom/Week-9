pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 shrishtishirisha1208/registration:v1'
                bat 'docker push shrishtishirisha1208/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f E:/DevOps/week2/deployment.yaml'
                bat 'kubectl apply -f E:/DevOps/week2/service.yaml'
            }
        }
    }
}
