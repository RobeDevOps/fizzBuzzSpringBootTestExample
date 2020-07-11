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
        stage('Generate Jar'){
            steps{
                sh "mvn clean install -B"
            }
        }
        stage('Running'){
            steps{
                // sh "SERVER_PORT=9093 mvn spring-boot:run"
                sh "tree ."
            }
        }
    }
}