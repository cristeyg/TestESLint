pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
               echo "Build Stage"
            }
        }
        stage('Test') {
            steps {
              echo "Test Stage"
            }
        }
        // Additional stages
    }
    post {
        always {
            echo "This is Jenkinsfile"
        }
    }
}