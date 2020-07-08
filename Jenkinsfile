pipeline {
    agent { label 'maven' }
    options {
        buildDiscarder(
            logRotator(
                numToKeepStr: '3',
                daysToKeepStr: '3'
            )
        )
    }
    stages{
        stage('Testing'){
            steps{
                sh "mvn test -B"
            }
        }
        stage('Running'){
            steps{
                sh "SERVER_PORT=9093 mvn spring-boot:run"
            }
        }
    }
}