pipeline
{
    
    agent any
    stages
    {
        stage("GIT checkout")
        {
            steps
            {
               git credentialsId: '1f1593df-82b9-4bdc-9b74-a863d52f969a', url: 'https://github.com/anusha198726/my-webapp-2.git'
            }
        }
         stage("Maven Build"){
            steps{
                sh "mvn clean package"
                 sh "mv target/*.war target/myweb.war"
                
            }
        }
         stage("deploy-dev"){
            steps{
                sshagent(['tomcat-new']) {
                sh "
                    scp -o StrictHostKeyChecking=no target/myweb.war  ubuntu@172.31.89.232:/var/lib/tomcat9/webapps/
                    "
            }
            
                    
                   
            }
            
}
    }
}
