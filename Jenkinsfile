pipeline {
    agent { label 'maven' }
    stages{
        stage('Checkout'){
            steps{
                git credentialsId: 'github-credentials', 
                    url: 'git@github.com:RobeDevOps/fizzBuzzSpringBootTestExample.git'
            }
        }
        stage('Verify'){
            steps{
                sh "ls -ltr"
            }
        }
    }
}