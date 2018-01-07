pipeline {
    agent any

    stages {
         stage('Build') {
            steps {
                        sh 'make'
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