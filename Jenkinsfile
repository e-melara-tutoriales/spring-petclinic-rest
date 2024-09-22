pipeline {
    agent {
        docker {
            image "maven:3.8.8-eclipse-temurin-17"
        }
    }

    stages {
        stage('Compile') {
            steps {
               sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                sh "mvn test -B -ntp"
                junit "target/surefire-reports/*.xml"
                jacoco()
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package -DskipTests -B -ntp'
            }
        }
    }

    // post {
    //     always {
            //archiveArtifacts artifacts: "target/*.jar", fingerprint: true
    //         cleanWs()
    //     }
    // }
}