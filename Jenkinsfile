pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh './build' 
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
            }
        }
    }
}
