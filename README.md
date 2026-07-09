# Jenkins CI/CD Delivery Project

This project builds and pushes a Docker image for a Python application using GitHub, Jenkins, Docker Engine, and Docker Hub.

## Files
- Mustafa.Zahid.py
- Dockerfile
- Jenkinsfile

## Run Python app locally
python3 Mustafa.Zahid.py

## Build Docker image
docker build -t mustafazahid/jenkins-python-app:latest .

## Run Docker container
docker run --rm mustafazahid/jenkins-python-app:latest

## CI/CD Flow
1. Code is pushed to GitHub.
2. GitHub triggers Jenkins.
3. Jenkins builds the Docker image.
4. Jenkins logs in to Docker Hub using stored credentials.
5. Jenkins pushes the image to Docker Hub.
