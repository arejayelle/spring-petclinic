pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                notifyStarted()
                sh './mvnw clean install'
                notifySuccessful()
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
                branch 'master'
            }
            steps {
                echo 'I am deploying because I am on master'
                
            }
        }

    }
}

def notifyStarted() {

  // send to email
  emailext (
      subject: "STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
      body: """
        STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':
                
        Check console output at "${env.JOB_NAME} [${env.BUILD_NUMBER}] "

        """,
      recipientProviders: [[$class: 'DevelopersRecipientProvider']]
    )
}

def notifySuccessful() {

  // send to email
  emailext (
      subject: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
      body: """
        SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':
                
        Check console output at "${env.JOB_NAME} [${env.BUILD_NUMBER}] "

        """,
      recipientProviders: [[$class: 'DevelopersRecipientProvider']]
    )
}
