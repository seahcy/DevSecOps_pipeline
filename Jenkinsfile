pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        stage("build & SonarQube analysis") {
          agent any
          steps {
            withSonarQubeEnv('sonarqube') {
              sh 'mvn clean package sonar:sonar'
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
