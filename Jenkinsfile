pipeline {
	agent any
	
	stages {
	    stage('Checkout') 
              {
	        steps 
                     {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/ubuntu/Downloads/apache-maven-3.6.0/bin/mvn install'
	              }}
		stage('Deployment'){
		    steps {
			
			sh 'cp /home/ubuntu/Documents/grras/amazon/target/shopclues.war /home/ubuntu/Downloads/apache-tomcat-9.0.71/webapps'
	              }}
}
post
{
always
{
emailext body: 'summary', subject: 'email notification', to: 'tusharmangre007@gmail.com'
}
}
}
