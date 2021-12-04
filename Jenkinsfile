pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean verify'
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