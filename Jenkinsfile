pipeline {
    agent any

    stages {

        stage('git project checkout') {
            steps {
               	git branch: 'main', url: 'https://github.com/sankalpmax/EV-Car-Application-CICD.git'
            }
        }

 	stage('Docker Build Image') {
            steps {
                sh 'docker build -t sankalparava/fintech-bank:01 . '
            }
        }
	stage('Docker Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name yubi sankalparava/fintech-bank:01'
			}
		}
	}
}
