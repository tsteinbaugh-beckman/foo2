pipeline {
    agent any
    
    stages {
        stage ('hello') {
            steps {
                echo 'hello'
                script {
                    def causes = currentBuild.rawBuild.getCauses()
                    echo causes
                }
            }
        }
        stage ('upstream trigger?') {
            when {
                triggeredBy upstreamCause: 'UserIdCause'
            }
            steps {
                echo 'YAY!'
            }
        }
        stage ('build next foo3') {
            steps {
                build job: 'test/foo3/main', propagate: false, wait: false
            }
        }
    }
}       
