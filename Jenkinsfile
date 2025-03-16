pipeline {
    agent any 
    
    stages {   
        stage('SCM Checkout') { // Clone the GitHub repository
            steps {
                retry(3) {
                    git branch: 'main', url: 'https://github.com/basuru07/GitHub-Docker-and-Jenkins-CI-CD-Pipeline'
                }
            }
        }
        stage('Build Docker Image') { // Build the Docker image
            steps {  
                bat 'docker build -t basuruyasaruwan/nodeapp-cuban:%BUILD_NUMBER% .'
            }
        }
        stage('Login to Docker Hub') { // Authenticate with Docker Hub
            steps {
                withCredentials([usernamePassword(credentialsId: 'test-dockerhubpassword', usernameVariable: 'DOCKERHUB_USERNAME', passwordVariable: 'DOCKERHUB_PASSWORD')]) {
                    script {
                        bat 'docker login -u %DOCKERHUB_USERNAME% -p %DOCKERHUB_PASSWORD%'
                    }
                }
            }
        }
        stage('Push Image') { // Push the built image to Docker Hub
            steps {
                bat 'docker push basuruyasaruwan/nodeapp-cuban:%BUILD_NUMBER%'
            }
        }
    }
    post {
        always {
            bat 'docker logout'
        }
    }
}
