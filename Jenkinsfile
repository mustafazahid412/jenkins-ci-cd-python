pipeline {
    agent any

    environment {
        IMAGE_NAME = "mustafazahid/jenkins-python-app"
        IMAGE_TAG = "${BUILD_NUMBER}"
    }

    stages {
        stage('Mustafa.Zahid - Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:$IMAGE_TAG -t $IMAGE_NAME:latest .'
            }
        }

        stage('Mustafa.Zahid - Login to Dockerhub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                }
            }
        }

        stage('Mustafa.Zahid - Push image to Dockerhub') {
            steps {
                sh 'docker push $IMAGE_NAME:$IMAGE_TAG'
                sh 'docker push $IMAGE_NAME:latest'
            }
        }
    }
}
