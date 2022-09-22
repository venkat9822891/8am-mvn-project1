node('master') 
{
    stage('Continuous Download') 
	{
    git 'https://github.com/sunildevops77/maven.git'
	}
    stage('Continuous Build') 
	{
    sh label: '', script: 'mvn package'
	}
    stage('Continuous Deployment') 
	{
sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war   ubuntu@http://43.204.30.155:/var/lib/tomcat8/webapps/qaenv.war'
	}
	post {
        always {
            emailext body: '''Dear Developer,

Build failed please look into this on priority and fix it

Thanks,
DevOps Team''', subject: 'BuildFailed', to: 'wnsadmi@gmail.com'
            
        }
    }
}
