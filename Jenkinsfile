pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                    bash -x ./build
                    export REPO=$REPO
                ''' 
            }
        }
    }
}
