pipeline {
        agent { label 'JDK8' }
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
	
