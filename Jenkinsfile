pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Code checked out from SCM'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package -DskipTests'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t demo-app:1.0 .'
            }
        }
    }

    post {
        success {
            echo 'Build and Docker image created successfully'
        }
        failure {
            echo 'Build failed'
        }
    }
}
