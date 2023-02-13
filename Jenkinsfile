pipeline {
    agent any
    tools{
maven "maven3.9.0"
}
    
 options([   
parameters([
    choice(
        choices:
        ['git'], name: 'TOOLS')])])
    
    
    stages {
        stage('checkout')
        {
            steps{
            git credentialsId: 'GITcredentials', url: 'https://github.com/padmasree1/maven-web-application.git'
            }
        }
        stage('build')
   {
      steps{
     sh "mvn clean package"
      }
   }
    }
}
