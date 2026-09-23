pipeline {
    agent any

    stages {

        stage('Build React') {
            steps {
                bat 'npm install'
                bat 'npm run build'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t react-counter .'
            }
        }

        stage('Deploy') {
            steps {
                bat '''
                    docker stop react-counter-pipeline 2>nul
                    docker rm react-counter-pipeline 2>nul
                    docker run -d --name react-counter-pipeline -p 8083:80 react-counter
                '''
            }
        }

    }
}