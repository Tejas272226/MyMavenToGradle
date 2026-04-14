pipeline {
    agent any  // Use any available agent

    tools {
        gradle 'Gradle'  // Ensure this matches the name configured in Jenkins
        jdk 'JDK'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Tejas272226/MyMavenToGradle.git'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle build'  // Run Gradle build
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test'  // Run unit tests
            }
        }

        
        
       
        stage('Package') {
            steps {
                // Start the JAR application
                sh 'gradle build'
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
