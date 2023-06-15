pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'main']], userRemoteConfigs: [[url: 'https://github.com/charan-git-official/service-1']]])
            }
        }
        
        stage('Build microservice') {
            steps {
                bat 'mvn clean package' // Assuming Maven is used for building
            }
        }
        
        stage('Build Docker image') {
            steps {
                bat 'docker build -t service-1 .'
            }
        }
    }
}
