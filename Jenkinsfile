pipeline {
    agent any
    tools {
        maven 'Maven' // This must match the name in Jenkins Global Tool Configuration
        jdk 'JDK'     // This must match the name in Jenkins Global Tool Configuration
    }
    stages {
        stage('Checkout') {
            steps {
                // Replace with your GitHub Repo URL
                git branch: 'main', url: 'https://github.com/harshitha7104/maven-hello-world.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Run Application') {
            steps {
                sh 'java -jar target/maven-hello-world-1.0-SNAPSHOT.jar'
            }
        }
    }
    post {
        success { echo 'Build and deployment successful!' }
        failure { echo 'Build failed!' }
    }
}
