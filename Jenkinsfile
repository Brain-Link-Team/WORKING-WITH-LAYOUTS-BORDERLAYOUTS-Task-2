pipeline {
    agent any
    tools { maven 'Maven-3.9'; jdk 'JDK-17' }
    stages {
        stage('Compile') {
            steps { bat 'mvn clean compile -B' }
        }
        stage('Test') {
            steps { bat 'mvn test -B' }
        }
        stage('Package') {
            steps { bat 'mvn package -DskipTests -B' }
        }
    }
    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }
    }
}