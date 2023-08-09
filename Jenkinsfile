pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './mvnw compile'
                sh './mvnw package'
            }
        }
        stage('Test') {
            steps {
                sh './mvnw test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
