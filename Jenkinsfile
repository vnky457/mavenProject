node('master') 
{
   
   stage('ContinuousDownload') 
    {
       git 'https://github.com/eml2raghu/maven.git'

    }
 
   
    
    stage('ContinuousBuild') 
    {
        
   	sh label: '', script: 'mvn package'

    }

  
    stage('ContinuousDeploy') 
    {
    
	sh label: '', script: 'scp /root/.jenkins/workspace/Scripted_Pipeline1/webapp/target/webapp.war ubuntu@172.31.9.223:/var/lib/tomcat8/webapps/test.war'

    }
  

    stage('ContinuousTesting') 
    {
      
     	git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
      sh label: '', script: 'java -jar /root/.jenkins/workspace/Scripted_Pipeline1/testing.jar'
  
    }


    stage('ContinuousDelivery') 
    {
    
	sh label: '', script: 'scp /root/.jenkins/workspace/Scripted_Pipeline1/webapp/target/webapp.war ubuntu@172.31.5.132:/var/lib/tomcat8/webapps/prod.war'

    }

    

}
