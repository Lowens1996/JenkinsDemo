pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'mvn clean compile'
                archiveArtifacts artifacts: '**/target/*.java', fingerprint: true
            }
        }
         stage('Deploy') {
                    when {
                      expression {
                        currentBuild.result == null || currentBuild.result == 'SUCCESS'
                      }
                    }
                    steps {
                        bat 'make publish'
                    }
                }
    }
}