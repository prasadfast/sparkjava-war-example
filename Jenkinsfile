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
			    
			    sh ' docker build  -t tomcat_new .'
		    }
	    }
	 stage('k8s') {
		    steps { 
			    sh 'docker-compose up -d'
		    }
	    }    
    }
}
