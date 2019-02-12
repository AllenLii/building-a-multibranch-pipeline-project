pipeline {
    agent { 
		docker {
			image 'node:6-alpine'
			args '-u root -p 3000:3000 -p 5000:5000'
			label 'linux'
		}
	}
	environment {
		CI = 'true'
	}
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
		stage('Test'){
			steps {
				sh './jenkins/scripts/test.sh'
			}
		}
    }
}
