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
        }
    }
    post {
        success {
            junit '**/target/surfire-reports/TEST-*.xml'
            archiveArtifacts artifacts: 'target/*.jar'
        }
    }
}
