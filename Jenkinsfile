pipeline {
    agent any
    environment {
        SONAR_AUTH_TOKEN = credentials('sonarqubeAuth')
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean verify -f ./JHotDraw'
            }
        }
        stage('Code Quality') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.login=$SONAR_AUTH_TOKEN -f ./JHotDraw'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}