pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Your build commands here
                    docker.build('muddasir5511/web-app:latest')
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Your test commands here
                    sh 'echo "Running tests"'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Your deployment commands here (e.g., SSH into EC2 and update container)
                    sh 'echo "Deploying to AWS EC2"'
                }
            }
        }
    }

    post {
        failure {
            // Rollback to the previous version on failed deployment
            script {
                // Your rollback commands here
                echo 'Rolling back to the previous version'
            }
        }

        unstable {
            // Additional actions for unstable builds
        }

        success {
            // Additional actions for successful builds
        }
    }
}
