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
                build: 'test/foo3/main'
            }
        }
    }
}       
