pipeline {
    agent any
    stages {
        stage('Initalize') {
            steps {
                checkout(
                          [$class: 'GitSCM', 
                            branches: [
                                        [name: '*/master']
                            ], 
                            doGenerateSubmoduleConfigurations: false, 
                            extensions: [
                                            [$class: 'SubmoduleOption', 
                                                disableSubmodules: false, 
                                                parentCredentials: false, 
                                                recursiveSubmodules: false,
                                                timeout: 180,
                                                reference: '', 
                                                trackingSubmodules: true
                                            ], 
                                            [$class: 'RelativeTargetDirectory', 
                                                relativeTargetDir: 'repo'
                                            ],
                                            [$class: 'CheckoutOption', 
                                                timeout: 180
                                            ]
                                        ], 
                            submoduleCfg: [], 
                            userRemoteConfigs: [[url: env.REPO]]
                        ]
                )
            }
        }

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
