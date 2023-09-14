pipeline {
	agent any
	
	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/swapnil/Documents/DevOps-Software/apache-maven-3.9.4/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			 if ( env.ENVIRONMENT == 'QA' ){
        			sh 'cp target/CICDWITHCONDITION.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps'
			 }
			else  ( env.ENVIRONMENT == 'UAT' ){
    				sh 'cp target/CICDWITHCONDITION.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps'
			}
			}}}	
}
