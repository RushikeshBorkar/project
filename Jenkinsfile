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
			sh "mvn clean install"
			sh " cp /root/project/target/LoginWebApp.war /mnt/servers/apache-tomcat-9.0.93/webapps/"
			sh "cd ../bin/"
			sh "./shutdown.sh"
			sh " ./startup.sh"
			
		}
	}
}	
}
