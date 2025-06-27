pipeline {
    agent any

    environment {
        IMAGE_NAME = "your-dockerhub-username/flask-cicd-demo"
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/your-username/flask-cicd-jenkins-docker.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'pytest tests/'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Docker Push') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                    sh 'docker push $IMAGE_NAME'
                }
            }
        }

        stage('Deploy (Optional)') {
            steps {
                echo 'Deployment step can go here (e.g., ssh to server, kubectl apply, etc.)'
            }
        }
    }
}
