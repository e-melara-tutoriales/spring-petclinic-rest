pipeline {
    agent any

    tools {
        maven 'maven3.8.8'
    }

    stages {
        stage('maven version') {
            steps {
               sh 'mvn --version'
            }
        }
    }
}