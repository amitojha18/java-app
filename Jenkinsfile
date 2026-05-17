pipeline {

    agent any

    stages {


        stage('Maven Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t java-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f java-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d --name java-container java-app'
            }
        }
    }
}




