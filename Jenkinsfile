pipeline {
    agent any

    tools {
        maven 'maven3.8.8'
    }

    stages {
        stage('mvn clean') {
            steps {
               sh 'mvn clean'
            }
        }
    }
}