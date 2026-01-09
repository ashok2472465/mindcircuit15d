pipeline {
    agent any

    stages {
        stage('Clone GIT Repo') {
            steps {
                echo 'Cloning code from Github Repo'
				git branch: 'main', url: 'https://github.com/devopstraininghub/mindcircuit15d.git'
            }
        }
		stage('Building Artifact') {
            steps {
                echo 'Building Artifact using maven build tool'
				sh 'mvn clean install'		
			
    }
}

stage('Deploy to tomcat') {
            steps {
                echo 'Deploying Artifact on the Tomcat'
				deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcatpipeline', path: '', url: 'http://54.160.218.6:8080/')], contextPath: 'pipeline', war: '**/*.war'
				
				   }
}

   }
}
