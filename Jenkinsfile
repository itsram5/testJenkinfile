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
      success       {
           mail  from: ''
           subject: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
           body: """<p>SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
           <p>Check console output at &QUOT;<a href='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>&QUOT;</p>""",
            to: 'ramanjaneya.naidu@gmail.com'
         }

       failure       {
            mail  from: '', replyTo: '',
            subject: "FAILURE : Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
          body: """<p>FAILURE : Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
            <p>Check console output at &QUOT;<a href='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>&QUOT;</p>""",
         to: 'ramanjaneya.naidu@gmail.com'

         }
     }

 }