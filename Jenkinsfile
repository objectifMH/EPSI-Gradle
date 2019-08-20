pipeline {
  agent any
  stages {
        stage('Compile') {
            steps {
                bat 'gradlew bootJar'
            }
        }
        stage('Unit Tests') {
            steps {
                bat 'gradlew test'
            }
            post {
                always {
                    junit '**/build/test-results/test/TEST-*.xml'
                }
            }
        }
      stage('Sonar Qube') {
            steps {
                bat 'gradlew sonarqube'
            }
      }
  }
}
