pipeline {
    agent any

    tools {
        gradle 'Gradle_8'   // Name from Jenkins → Global Tool Configuration
        jdk 'JDK17'         // Optional, if your Jenkins uses JDK 17
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building project with Gradle...'
                sh './gradlew clean build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './gradlew test'
            }
            post {
                always {
                    junit '**/build/test-results/test/*.xml'
                }
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging artifact...'
                archiveArtifacts artifacts: 'build/libs/*.jar', fingerprint: true
            }
        }
    }

    post {
        success {
            echo '✅ Gradle build successful!'
        }
        failure {
            echo '❌ Gradle build failed!'
        }
    }
}
