
pipeline {
    agent any  // Use any available agent

    tools {
    maven 'Maven'
    jdk 'JDK'
}

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Sushpatil12/Maventogradle1.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Run Maven build
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // Run unit tests
            }
        }

        
        
       
        stage('Run Application') {
            steps {
                // Start the JAR application
                sh 'java -jar target/Maventogradle1-1.0-SNAPSHOT.jar'
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
