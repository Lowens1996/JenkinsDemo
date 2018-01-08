pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'mvn compile'
            }
        }
        stage('Run unit test') {
            steps {
                bat 'mvn test'
            }
        }
    }
}
