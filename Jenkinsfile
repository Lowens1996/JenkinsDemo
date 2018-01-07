pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'make'
                archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
            }
        }
         stage('Deploy') {
                    when {
                      expression {
                        currentBuild.result == null || currentBuild.result == 'SUCCESS'
                      }
                    }
                    steps {
                        sh 'make publish'
                    }
                }
    }
}