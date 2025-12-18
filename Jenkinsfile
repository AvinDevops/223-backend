pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('Xterm')
    }
    stages {
        stage ('Install Dependencies') {
            steps {
                sh """
                npm install
                ls -ltr
                """
            }
        }
    }
    post {
        always {
            echo 'I will run pipeline always, success or failure'
            deleteDir()
        }
        success {
            echo 'I will run when pipeline is success'
        }
        failure {
            echo 'I will run when pipeline is failure'
        }
    }
}