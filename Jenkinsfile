pipeline {
    agent any
 
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh '''
                        sonar-scanner \
                        -Dsonar.projectKey=django-devsecops \
                        -Dsonar.sources=.
                    '''
                }
            }
        }
    }
}
