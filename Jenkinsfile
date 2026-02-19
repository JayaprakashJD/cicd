pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/your-username/cicd-demo-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-demo .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop cicd-container || true'
                sh 'docker rm cicd-container || true'
                sh 'docker run -d -p 80:80 --name cicd-container cicd-demo'
            }
        }
    }
}
