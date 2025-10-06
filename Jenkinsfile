pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub...'
                checkout scm
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling Java code...'
                // For Windows
                bat 'javac -d bin src\\*.java'
                
               
              
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                // Replace 'Hello' with your main class name
                bat 'java -cp bin Hello'

              
            }
        }
    }

    post {
        success {
            echo 'Build and run completed successfully!'
        }
        failure {
            echo 'Build failed. Check errors above.'
        }
    }
}
