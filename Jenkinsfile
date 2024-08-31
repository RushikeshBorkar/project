pipeline {
 agent {
	 label{
                    label "built-in"
                     customWorkspace "/root/project"		
                   }
 }
	
stages {
	 stage("one"){
	    
		steps{
			sh "rm -rf /root/.m2/repository"
			sh "cd /root/project"
			sh "mvn clean install"
			sh " cp /root/project/target/LoginWebApp.war /mnt/server/apache-tomcat-9.0.93/webapps/"
			sh "cd /mnt/server/apache-tomcat-9.0.93/bin"
			
			
			
		}
	}
}	
}
