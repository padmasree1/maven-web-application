pipeline {
    agent any
    tools{
maven "maven3.9.0"
}
    
    
parameters([
    choice(
        choices:
        ['git'], description: '', name: 'TOOLS')])
    
    
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
