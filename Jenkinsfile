pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling Java program...'
                bat 'javac Hello.java'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                use: bat 'java Hello'
            }
        }
    }

    post {
        success {
            echo 'CI/CD pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check errors!'
        }
    }
}
