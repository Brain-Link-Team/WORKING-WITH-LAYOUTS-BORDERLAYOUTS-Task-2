pipeline {
    agent any
    tools { maven 'Maven-3.9'; jdk 'JDK-17' }
    stages {
        stage('Compile') {
            steps { sh 'mvn clean compile -B' }
        }
        stage('Test') {
            steps { sh 'mvn test -B' }
        }
        stage('Package') {
            steps { sh 'mvn package -DskipTests -B' }
        }
    }
}