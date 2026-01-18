pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: '<https://github.com/ArpitMetkar26/github-webhook-pipeline>.git'
            }
        }

        stage('Build') {
            steps {
                echo "Build started"
                sh 'echo Hello Jenkins'
            }
        }
    }

    post {
        success {
            mail to: 'your-email@gmail.com',
                 subject: "✅ Jenkins Build SUCCESS",
                 body: "Build #${BUILD_NUMBER} succeeded."
        }
        failure {
            mail to: 'your-email@gmail.com',
                 subject: "❌ Jenkins Build FAILED",
                 body: "Build #${BUILD_NUMBER} failed."
        }
    }
}
