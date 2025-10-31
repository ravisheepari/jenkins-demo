pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building project...'
                sh 'echo "Simulating build process..."'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo "Simulating tests..."'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'echo "Simulating deployment..."'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment completed successfully.'
        }
        failure {
            echo 'Build failed. Check logs for details.'
        }
    }
}
