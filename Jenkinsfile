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

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('local sonarqube'){
                    sh 'mvn sonar:sonar -Dsonar.login=$SONAR_AUTH_TOKEN -f ./JHotDraw'
                }
            }
        }

        stage('Quality Check') {
            steps {
                waitForQualityGate abortPipeline: true
            }
        }
    }
}