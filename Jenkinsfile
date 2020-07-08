pipeline
{
	agent any
	stages
	{
		stage('Checkout')
		{
			steps
			{
				git 'https://github.com/iamdevopstrainer/DevOpsClassCodes'
			}
		}
		
		stage('Compile')
		{
			steps
			{
				sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven_3.6.3/bin/mvn compile'
			}
		}

		stage('Test')
		{
			steps
			{
				sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven_3.6.3/bin/mvn test'
			}
		}

		stage('Build')
		{
			steps
			{
				sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven_3.6.3/bin/mvn package'
			}
		}
		
		stage('Deployment')
		{
			steps
			{
				echo "Deployment"
				sh 'cd /usr/share/tomcat/webapps/'
				sh 'cp /var/lib/jenkins/workspace/AddressBookPipeline/target/addressbook.war .'
				sh 'systemctl restart tomcat'
			}
		}
	}
		
}
