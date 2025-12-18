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
        stage ('Read Version') {
            steps {
                script {
                  def packageJson = readJSON file: 'package.json'
                  def appVersion = packageJson.version
                  echo "application version: $appVersion"
                }
            }
        }
        stage ('Install Dependencies') {
            steps {
                sh """
                ls -ltr
                echo 'application version: $appVersion'
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