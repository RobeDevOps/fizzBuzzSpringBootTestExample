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
                sh "mvn clean install -Dmaven.test.skip=true -B"
                sh "tree src"
            }
        }
        stage('Deploying the server'){
            steps{
                sh "cp src/target/gs-rest-service-0.1.0.jar /home/pi/deploy"
                dir("/home/pi/deploy"){
                    sh "tree ."
                    sh "SERVER_PORT=9093 mvn spring-boot:run"
                }                
            }
        }
    }
}