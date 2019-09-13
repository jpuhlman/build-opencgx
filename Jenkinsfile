pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                export REPO=$REPO
                sh 'bash -x ./build' 
            }
        }
    }
}
