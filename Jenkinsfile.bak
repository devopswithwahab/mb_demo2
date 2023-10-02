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
    		sh 'scp  /home/ubuntu/.jenkins/workspace/DemoPipeline/webapp/target/webapp.war   ubuntu@172.31.26.203:/var/lib/tomcat9/webapps/qaenv.war'
	}
    stage('Continuous Testing') 
	{
    		sh 'echo "testing passed"'
	}
    stage('Continuous Delivery') 
	{
    		sh 'scp  /home/ubuntu/.jenkins/workspace/DemoPipeline/webapp/target/webapp.war   ubuntu@172.31.24.2:/var/lib/tomcat9/webapps/prodenv.war'
	}
}
