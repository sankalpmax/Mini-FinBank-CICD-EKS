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
    }
}
