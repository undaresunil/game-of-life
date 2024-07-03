pipeline {
        agent { label 'JDK8' }

	environment {
        	MVN_3.6.3 = 'true'
        	MAVEN_HOME = '/opt/apache-maven-3.6.3'
    	}

        stages {
                stage('SourceCode') {
                        steps {
                                git branch: 'sunil24', url: 'https://github.com/undaresunil/game-of-life.git'
                        }
                }
                stage('Build the code') {
			steps {
				sh 'mvn clean package'
			}		
		}
		stage('Archiving and Test Result'){
			steps {
				junit stdioRetention: '', testResults: '**/surefire-reports/*.xml'
				archiveArtifacts artifacts: '**/*.war', followSymlinks: false
			}
		}
		}

}
	
