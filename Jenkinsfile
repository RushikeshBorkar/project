pipeline {
 agent {
	 label{
                    label "built-in"
                     customWorkspace "/mnt/project"		
                   }
 }
	
stages {
	 stage("one"){
	    
		steps{
			sh "rm -rf /root/.m2/repository"
			sh "cd /mnt/project"
			sh "mvn clean install"
			sh " cp /mnt/project/target/LoginWebApp.war /mnt/servers/apache-tomcat-9.0.94/webapps/"
					
		}
	}
}	
}
