
pipeline {
    agent any

    tools {
        maven 'Maven'   // configure in Jenkins tools
        jdk 'Java17'    // configure in Jenkins tools
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/AdityaK05/gradle-pipeline-app.git'
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

        stage('Run') {
            steps {
                sh 'java -jar target/*.jar'
            }
        }
    }

    post {
        success {
            echo 'Build Successful 🚀'
        }
        failure {
            echo 'Build Failed ❌'
        }
    }
}
