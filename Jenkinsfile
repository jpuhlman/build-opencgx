pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                    bash -x ./bin/build
                    export REPO=$REPO
                ''' 
            }
        }
    }
}
