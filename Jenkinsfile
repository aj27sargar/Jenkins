pipeline {
    agent any

    stages {

        stage('Check Environment') {
            steps {
                bat 'node --version'
                bat 'npm --version'
                bat 'docker --version'
            }
        }

    }
}