pipeline {
	    agent any
	    tools {
	        maven 'maven'   
	        }
		
	    stages {
	        stage ('Git Checkout') {
	            steps {
	                git branch: 'main',
			credentialsId: '030cb730-fcad-45a8-bd23-4e21aab05ad2',
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
		
    		
	
	}
}
