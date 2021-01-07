pipeline {
	    agent any
	    tools {
	        maven 'maven'   
	        }
	    stages {
	        stage ('Git Checkout') {
	            steps {
	                git branch: 'main',
			credentialsId: 'e44fda00-9ca2-439c-aeb9-e2e491c4f02b',
			url: 'https://github.com/shashisingh1998/code.git'
	                }
	            } 
		stage ('Compile') {
	            steps {
	                sh 'mvn compile'
	                }
	            }      
	        stage ('Package') {
	            steps {
	                sh 'mvn package'
	                }
	            }
	        stage ('Install') {
	            steps {
	                sh 'mvn install'
	                }
	            }
		    
		 stage ('Create war file') {
	            steps {
	                sh 'jar -cf target/dependency/webapp-runner.jar target/*.war'
	                }
	            }
		    
                stage ('Deploy War File') {
                        steps {
                                sh "cp target/*.war /home/ec2-user/apache-tomcat-8.5.61/webapps"
                        }
                }
	}
}
