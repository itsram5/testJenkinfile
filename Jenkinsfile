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
    }
   post {
         success {
                   mail   subject: " SUCCESS : Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                    body: "Please go to ${BUILD_URL} and verify the build" ,
                    to: 'ramanjaneya.naidu@gmail.com'
                 }

          failure {
                  mail   subject: " FAILURE : Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                  body: "Please go to ${BUILD_URL} and verify the build" ,
                  to: 'ramanjaneya.naidu@gmail.com'
                }
     }
 }