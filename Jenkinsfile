
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
      always       {
       mail  to: 'ramanjaneya.naidu@gmail.com'
         }

     }

 }