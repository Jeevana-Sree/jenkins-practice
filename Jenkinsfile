pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/Jeevana-Sree/jenkins-practice'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-html-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8080:80 --name my-html-app-container my-html-app'
            }
        }
    }
}

