pipeline {
 agent {
	 label{
                    label "built-in"
                     customWorkspace "/mnt/project"		
                   }
 }
 
 environment {
        AWS_ACCESS_KEY_ID = credentials("AKIAYS2NSLOT66DA645D")
        AWS_SECRET_ACCESS_KEY = credentials("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")
        DB_HOST = "database-2.cn00wsesmxwm.us-west-1.rds.amazonaws.com"
        DB_USER = "admin"
        DB_PASSWORD = credentials("pass12345")
        DB_NAME = "test"
        EC2_INSTANCE_ID = "i-0671d82165bc52346"
    }

	
stages {
	 stage("one"){
	    
		steps{
			sh "rm -rf /root/.m2/repository"
			sh "cd /mnt/project"
			sh "mvn clean install"
			sh " cp /mnt/project/target/LoginWebApp.war /mnt/server/apache-tomcat-9.0.93/webapps/"
					
		}
	}
	 
	 stage('Connect EC2 to RDS') {
            steps {
                
                    // Test connection to RDS from EC2
                    sh '''
                        ssh -i /mnt/cali-moba.pem ec2-user@${EC2_INSTANCE_ID} << EOF
                        mysql -h ${DB_HOST} -u ${DB_USER} -p${DB_PASSWORD} -e "SHOW DATABASES;"
                        EOF
                    '''
                
            }
        }
	
	
}	


}
