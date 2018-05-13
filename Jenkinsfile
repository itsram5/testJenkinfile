pipeline {
    agent any
    def mvnTool = tool 'mvn_3.5.3'
    stages {
        stage('Build') {
            steps {

                  sh "${mvnTool}/bin/mvn clean compile"

            }
        }
        stage('Test') {
           steps {

                   sh "${mvnTool}/bin/mvn test"

                  }
        }

    }
}