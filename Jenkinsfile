pipeline {
	agent  any 
    stages {
        stage('pull') {
		     steps { 
		                checkout scm	 
			 }
		}
		stage('Build') { 
            steps {
                sh 'mvn clean package ' 
            }
        }
	    stage('docker') {
		    steps { 
			    sh ' sudo docker build -t tomcat:8.0 .'
		    }
	    }
	    
    }
}
