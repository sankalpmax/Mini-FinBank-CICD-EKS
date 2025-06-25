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

        stage('Docker Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name yubi sankalparava/fintech-bank:01'
            }
        }

        stage('Docker Push') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerhub') {
                        docker.image('sankalparava/fintech-bank:01').push()
                    }
                }
            }
        }

        stage('SonarQube Scan') {
            steps {
                withSonarQubeEnv('sonar') {
                    sh '/opt/sonar-scanner/bin/sonar-scanner'
                }
            }
        }
    }
}

