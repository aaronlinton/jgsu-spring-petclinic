pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './mnvw package'
            }
        }
        stage('Test') {
            steps {
                sh './mnvw test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
