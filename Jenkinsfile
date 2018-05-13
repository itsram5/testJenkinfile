pipeline {
    agent any
    stages {
        stage('Build') {

            steps {
                               withMaven(maven: 'mvn_3.5.3') {
                                sh 'mvn clean compile'
                                }
                              }
        }
        stage('Test') {
            steps {
                   withMaven(maven: 'mvn_3.5.3') {
                    sh 'mvn test'
                    }
                  }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
    }
}