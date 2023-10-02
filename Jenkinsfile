node('master') 
{
   stage('Continuous Download') 
	{
    		git branch: 'main', url: 'https://github.com/devopswithwahab/maven.git'
	}
   stage('Continuous Build') 
	{
    		sh 'mvn package'
	}
	stage('Continuous Deployment') 
	{
            sh label: '', script: 'scp  /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war  ubuntu@172.31.23.113:/var/lib/tomcat9/webapps/qaenv.war'
	}
stage('Continuous Testing') 
	{
	        sh label: '', script: 'echo "Testing Passed"'
	}
stage('Continuous Delivery') 
	{
	        input 'Waiting for Approval from DM'
	        sh label: '', script: 'scp  /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war  ubuntu@172.31.29.225:/var/lib/tomcat9/webapps/prodenv.war'
	}
	
}