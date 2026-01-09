pipeline {
    agent any

    stages {
	
        stage('CLONE GITHUB CODE') {
            steps {
                echo 'In this stage code will be clone'
				git branch: 'main', url: 'https://github.com/devopstraininghub/mindcircuit15d.git'
				
				}
        }
		
        stage('BUILDING THE CODE') {
            steps {
                echo 'In this stage code will be build and mvn artifact will be generated'
				sh 'mvn clean install '
				
            }
        }		
		
        stage('DEPLOY') {
            steps {
                echo 'In this stage .war artiface will be deployed on to tomcat '
				deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcatpipeline', path: '', url: 'http://54.160.218.6:8080/')], contextPath: 'pipeline', war: '**/*.war'
				
            }
        }		
		
		
    }
}
