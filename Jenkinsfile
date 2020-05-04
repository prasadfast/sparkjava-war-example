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
			    sh ' docker build  -t tomcat.8.0 .'
		    }
	    }
	 stage('k8s') {
		    steps { 
			    sh 'ansible all -m ping -K redhat '
		    }
	    }    
    }
}
