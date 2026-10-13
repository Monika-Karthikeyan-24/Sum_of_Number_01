
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Getting project source code'
                checkout scm
            }
        }

        stage('Build and Test') {
            steps {
                bat 'mvn clean test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'Addition Maven project completed successfully!'
        }
        failure {
            echo 'Build or JUnit test failed!'
        }
    }
}
