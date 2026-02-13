pipeline {
    agent any

    stages {
        stage('Code clone') {
            steps{
                echo "Clone the project"
                git url : "https://github.com/biswajit134/Node-app.git", branch: "main"
                echo "Code clone sucessfully"
                sh "pwd"
            }
        }
        stage('Test') {
            steps{
                echo "Test the code"
                // sh "npm ci"
                // sh "npm run test"
                // echo "Test sucessfully"
            }
        }
        stage('Build') {
            steps{
                echo "Build the docker file"
                sh "whoami"
                sh "docker build -t biswajit134/task2 ."
                echo "Build sucessfully"
            }
        }
        stage('Push to dockerhub') {
            steps{
                echo "Push image in Dockerhub"
                withCredentials([usernamePassword('credentialsId':"dockerHubCred", passwordVariable:"dockerHubPass", usernameVariable: "dockerHubUser")]){
                    sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                    sh "docker push ${env.dockerHubUser}/task2:latest"
                
                }
                echo "Push sucessfully"

            }
        }
        stage('Deploy') {
            steps{
                echo "Run the container"
            }
        }
    }
}