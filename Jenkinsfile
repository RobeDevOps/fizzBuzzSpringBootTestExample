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
                // sh "mvn test -B"
                echo "test here"
            }
        }
        stage('Generate Jar'){
            steps{
                sh "mvn clean install -Dmaven.test.skip=true -B"
                sh "tree target"
            }
        }
        stage('Deploying the server'){
            steps{
                dir("/home/pi/deploy"){
                    sh "cp ${WORKSPACE}/target/gs-rest-service-0.1.0.jar ."
                    sh "tree ."
                    sh "SERVER_PORT=9093 mvn spring-boot:run"
                }                
            }
        }
    }
}