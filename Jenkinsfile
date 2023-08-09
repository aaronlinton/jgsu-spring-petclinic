pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './mvnw clean package'
            }
            post {
                success {
                    junit '**/target/surfire-reports/TEST-*.xml'
                    archiveArtifacts artifacts: 'target/*.jar'
                }
            }
        }
    }
}
