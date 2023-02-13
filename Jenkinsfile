pipeline {
    agent any
    tools{
maven "maven3.9.0"
}
    
    
    
    stages {
        
       stage('Setup parameters') {
            steps {
                script { 
                    properties([
                        parameters([
                            choice(
                                choices: ['git'], 
                                name: 'TOOLS'
                            )
                         
                        ])])
                    
			  
                }
	  
			  
            }
        }
	stage('version')
	{
		steps{
			sh 'git --version'
		}
		
	}	
			    
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
	    
stage("build docker image")
{
	steps{
 sh "docker build -t apache:2.0 ."
		sh "docker ps -a"
	
	}
}
    }
}
