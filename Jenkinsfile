pipeline{
    agent any
    stages{
        stage("GIT checkout"){
            steps{
                git credentialsId: 'javahome', url: 'https://github.com/srinivas1987devops/myweb.git'
                
            }
        }
