pipeline {
    agent any
    stages {

        stage('Checkout') {
            steps {
                 git branch: 'main', url: 'https://github.com/sankalpmax/Mini-FinBank-CICD-EKS.git'
            }
        }

         stage('Docker Build Image') {
            steps {
                sh 'docker build -t sankalparava/fintech-bank:01 .'
		            }
       		 }
 	stage('Docker Build Image') {
            steps {
                sh 'docker run -d -p 5000:5000 --name yubi sankalparava/fintech-bank:01'
			}
		}
	}

}
