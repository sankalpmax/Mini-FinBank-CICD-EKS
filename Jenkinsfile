pipeline {
    agent any
    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/sankalpmax/Mini-Fin'
            }
        }

         stage('Docker Build Image') {
            steps {
                sh 'docker build -t sankalparava/ev-car:02 .'
            }
        }

        stage('SonarQube Scan') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh 'sonar-scanner'
        }
    }
}

            stage('Docker Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name yubi sankalparava/fintech-bank:01'
            }
        }
    }
}
