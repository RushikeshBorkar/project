pipeline{
	agent{
	node{
	label "built-in"
	customWorkspace "/home/ec2-user/project1"
	}
	
	}
		stages{
			stage("clone"){
				steps{
				sh "rm -rf *"
				sh "sudo git clone https://github.com/RushikeshBorkar/project.git -b dev"
				}
			
			}
			
			stage("build"){
			steps{
			sh "sudo rm -rf /home/ec2-user/.m2/repository"
			sh "mvn -f /home/ec2-user/project1/project clean install"
			}
			
			}
			
			stage("deploy"){
			steps{
			
			sh "sudo scp -i /home/ec2-user/moba.pem -o StrictHostKeyChecking=no /home/ec2-user/project1/project/target/LoginWebApp.war ec2-user@172.31.31.151:/home/ec2-user/home/ec2-user/apache-tomcat-9.0.98/webapps"
			
			}
			
			}
			
			
		
		}

}
