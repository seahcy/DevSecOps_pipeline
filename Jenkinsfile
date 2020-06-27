pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
         stage('SonarQube analysis') {
             environment {
                SCANNER_HOME = tool 'SonarScanner'
             }
             steps {
                withSonarQubeEnv('sonarqube') { // If you have configured more than one global server connection, you can specify its name
                  sh "${SCANNER_HOME}/bin/sonar-scanner -D sonar.login=admin -D sonar.password=admin"
                }
             }
            
          }
        stage('build') {
            steps {
                sh 'python test1.py'
            }
        }
    }
}
