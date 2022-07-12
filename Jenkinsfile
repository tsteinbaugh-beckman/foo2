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
                build: 'foo3'
            }
        }
    }
}       
