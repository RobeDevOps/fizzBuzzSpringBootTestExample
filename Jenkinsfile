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
        stage('test'){
            steps{
                sh "mvn test -B"
            }
        }
    }
}