pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean verify -f ./JHotDraw'
            }
        }
        stage('Code Quality') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}