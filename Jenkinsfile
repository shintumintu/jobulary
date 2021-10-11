pipeline {
    agent any

    stages {
        stage('TEST') {
            steps {
                sh 'flutter test'
            }
        }
        stage('BUILD') {
            steps {
                sh '''
                  #!/bin/sh
                  flutter build web
                  '''
            }
        }
    }
    post{
        success{
            emailext body: '''Hi Mintu,
  The Jobulary_Pipeline was Runned Successfully''', subject: 'Jobulary_Pipeline ', to: 'mintushintu41@gmail.com'
        }
    }
}
