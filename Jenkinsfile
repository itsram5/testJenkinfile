pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                withMaven(maven: 'Maven 3.3.9') {
                  sh 'mvn clean compile'
                }
            }
        }
        stage('Test') {
           steps {
                   withMaven(maven: 'Maven 3.3.9') {
                    sh 'mvn test'
                    }
                  }
        }
        stage('Deploy') {
            steps {
                   withMaven(maven: 'Maven 3.3.9') {
                    sh 'mvn clean compile'
                    }
                  }
        }
    }
}


