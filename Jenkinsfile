pipeline {
    agent any

    tools {
        jdk 'defaultJDK' // Ensure this matches the name you gave the JDK installation in Jenkins
        maven 'defaultMaven' // Ensure this matches the name you gave the Maven installation in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
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
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
        }
    }
}
