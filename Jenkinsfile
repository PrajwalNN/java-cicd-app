pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/YOUR-USERNAME/java-cicd-app.git'
            }
        }

        stage('Build Maven Project') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t java-cicd-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run --name java-app-container java-cicd-app'
            }
        }
    }
}
