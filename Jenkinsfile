pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        stage("build & SonarQube analysis") {
          agent any
          steps {
            def scannerHome = tool 'SonarScanner 4.0';
            withSonarQubeEnv('sonarqube') {
              sh "${scannerHome}/bin/sonar-scanner"
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
