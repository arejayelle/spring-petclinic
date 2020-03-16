pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './mvnw package'

            }
        }
        stage('test') {
            steps {
                echo 'I am testing'
                
            }
        }
        stage('package') {
            steps {
                echo 'I am packaging'
                
            }
        }

        stage('deploy') {
            steps {
                echo 'I am deploying because I am on master'
                
            }
        }
    }
}
