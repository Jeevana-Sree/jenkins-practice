pipeline {
    agent any

    triggers {
        pollSCM('H/15 * * * *')
    }

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/username/jenkins-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('my-html-app')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker rm -f html-app || true'
                    sh 'docker run -d --name html-app -p 8080:80 my-html-app'
                }
            }
        }
    }
}
