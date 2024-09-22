pipeline {
    agent {
        docker {
            image "maven:3.8.8-eclipse-temurin-17"
        }
    }

    stages {
        stage('Package') {
            steps {
                sh 'mvn clean package -DskipTests -B -ntp'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: "target/*.jar", fingerprint: true
            cleanWs()
        }
    }
}