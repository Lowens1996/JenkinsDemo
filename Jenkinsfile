pipeline {
    agent any
    stages {
        stage('Compile Code Stage') {
            steps {
                bat 'mvn -B -DskipTests clean package'
            }
        }
    }
}
