@Library('jenkins-lib') _

pipeline {
    agent any

    environment {
        IMAGE_NAME = "demo-app"
        IMAGE_TAG  = "v1"
    }

    stages {
        stage('Build') {
            steps {
                mavenBuild()
            }
        }

        stage('Test') {
            steps {
                mavenTest()
            }
        }

        stage('Docker Build') {
            steps {
                dockerBuild(IMAGE_NAME, IMAGE_TAG)
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully using Shared Library'
        }
    }
}
