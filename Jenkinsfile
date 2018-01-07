pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                withMaven(maven: 'Maven'){
                    bat 'mvn clean compile'
                }
            }
        }
         stage('Deploy') {
                    when {
                      expression {
                        currentBuild.result == null || currentBuild.result == 'SUCCESS'
                      }
                    }
                    steps {
                        withMaven(maven: 'Maven'){
                            bat 'mvn deploy'
                        }
                    }
                }
    }
}