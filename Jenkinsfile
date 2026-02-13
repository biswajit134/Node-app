pipeline {
    agent any

    stages {
        stage('Code clone') {
            steps{
                echo "Clone the project"
                
                
            }
        }
        stage('Test') {
            steps{
                echo "Test the code"
            }
        }
        stage('Build') {
            steps{
                echo "Build the docker file"
            }
        }
        stage('Push') {
            steps{
                echo "Push image in Dockerhub"
            }
        }
        stage('Deploy') {
            steps{
                echo "Run the container"
            }
        }
    }
}