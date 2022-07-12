pipeline {
    agent any
    
    stages {
        stage ('hello') {
            steps {
                echo 'hello'
            }
        }
        stage ('upstream trigger?') {
            when {
                triggeredBy 'BuildUpstreamCause'
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
