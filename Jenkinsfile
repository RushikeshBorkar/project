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
			sh "cd /root/project"
			sh "mvn clean install"
			sh " cp /root/project/target/LoginWebApp.war /mnt/server/apache-tomcat-9.0.93/webapps/"
			sh "cd ../bin/"
			sh "./shutdown.sh"
			sh " ./startup.sh"
			
		}
	}
}	
}
