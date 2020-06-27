pipeline {
    agent none
    stages {
        
        
        
         stage('SonarQube analysis') {
             agent { docker { image 'sonar-scanner:latest' } }
             environment {
                SCANNER_HOME = tool 'SonarScanner'
             }
             steps {
                withSonarQubeEnv('sonarqube') { // If you have configured more than one global server connection, you can specify its name
                  sh "${SCANNER_HOME}/bin/sonar-scanner"
                }
             }
            
          }
        
        
        
        
        
        stage('build') {
            agent { docker { image 'python:3.5.1' } }
            steps {
                sh 'python test1.py'
            }
        }
    }
}
