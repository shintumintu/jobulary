def appname ="Runner"
def xcarchive = "${appname}.carchive"

pipeline {
    agent any
    
    stages {
        
        stage ('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('TEST') {
            steps {
                bat 'flutter test --coverage test/widget_test.dart'
            }
        }
        stage('BUILD') {
            steps {
                bat '''
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
