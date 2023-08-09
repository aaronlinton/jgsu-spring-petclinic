pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './mvnw compile'
                sh './mvnw package'
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
        stage('Test') {
            steps {
                sh './mvnw test'
            }
//            post {
//                always {
//                    junit 'target/surefire-reports/*.xml'
//                }
//            }
        }
    }
}
