pipeline {
    agent any

    stages {

        stage('git project checkout') {
            steps {
               	git branch: 'main', url: 'https://github.com/sankalpmax/EV-Car-Application-CICD.git'
            }
        }
    }
}
