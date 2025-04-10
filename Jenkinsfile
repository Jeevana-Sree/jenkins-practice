pipeline {
    agent any

    triggers {
        pollSCM('H/15 * * * *') // optional
    }

    stages {
        stage('Clone Repo') {
            steps {
                git url: 'https://github.com/Jeevana-Sree/jenkins-practice'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("my-html-app")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    dockerImage.run("-d -p 8080:80")
                }
            }
        }
    }
}

