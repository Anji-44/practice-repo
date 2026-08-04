pipeline {
    agent any

    tools {
        maven 'MyMaven' // Ensure this version is configured in Jenkins
        jdk 'MyJDK'      // Ensure this JDK version is configured in Jenkins
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from SCM
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Build the project using Maven
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Run unit tests
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                // Package the application
                sh 'mvn package'
            }
        }

        stage('Verify') {
            steps {
                echo 'Verifying the application...'
                sh 'ls -l target'
            }
        }

        stage('Java Version') {
            steps {
                sh 'java -version'
            }
        }

        stage('Maven Version') {
            steps {
                sh 'mvn -version'
            }
        }

        stage('Workspace') {
            steps {
                sh 'pwd'
            }
        }

        stage('List Files') {
            steps {
                sh 'ls -la'
            }
        }
       
        stage('Environment') {
            steps {
                sh 'printenv'
            }
        }

        stage('Git Version') {
            steps {
                sh 'git --version'
            }
        }
        
        stage('Current User') {
            steps {
                sh 'whoami'
            }
        }

        stage('Deploy') {
            steps {
                // Simple deployment example
                sh 'echo "Deploying application..."'
                // Example of copying artifacts to a deploy location
                sh 'cp target/basic-java-app-1.0-SNAPSHOT.jar .'
            }
        }
    }

    post {
        always {
            // Clean up actions
            sh 'echo "Cleaning up..."'
        }

        success {
            // Actions on successful build
            echo 'Build succeeded!'
        }

        failure {
            // Actions on failed build
            echo 'Build failed!'
        }
    }
}
