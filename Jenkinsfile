pipeline {
    agent any
    
    stages {
        stage ('hello') {
            steps {
                echo 'hello'
            }
        }
        stage ('build next foo3') {
            steps {
                script {
                    try {
                        build(
                            job: "test/foo3/${param.originalFeatureBranch}", 
                            propagate: false, 
                            wait: false,
                            parameters: originalFeatureBranch = env.BRANCH_NAME)
                    }
                    catch (err) {
                        build(
                            job: 'test/foo3/main', 
                            propagate: false, 
                            wait: false,
                            parameters: originalFeatureBranch = env.BRANCH_NAME)
                    }
                }
            }
        }
    }
}    
