pipeline {
    agent { label 'maven' }
    options {
        buildDiscarder(
            logRotator(
                numToKeepStr: 3,
                daysToKeepStr: 3
            )
        )
    }
    stages{
        stage('Verify'){
            steps{
                sh "ls -ltr"
            }
        }
    }
}