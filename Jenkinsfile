pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './mvnw clean install'
                
            }
        }
        stage('Test') {
            steps {
                echo 'I am testing'
                sh './mvnw test'
                
            }
        }
        stage('Package') {
            steps {                
                echo 'I am packaging'
                sh './mvnw package'
                
            }
        }

        stage('Deploy') {
            when{
                expression{choice == 'master'}
            }
            steps {
                echo 'I am deploying because I am on master'
            
          )
                
            }
        }
    }
}
