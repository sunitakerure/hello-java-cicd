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
                // Create bin folder if missing
                bat 'if not exist bin mkdir bin'

                // Compile Java files with Java 8 compatibility
                bat 'javac --release 8 -d bin src\\demoPackage\\Hello.java'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                // Use full package name when running
                bat 'java -cp bin demoPackage.Hello'
            }
        }
    }

    post {
        success {
            echo '✅ Build and run completed successfully!'
        }
        failure {
            echo '❌ Build failed. Check errors above.'
        }
    }
}