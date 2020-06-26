pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        
          stage("build & SonarQube analysis") {
              node {
                  withSonarQubeEnv('My SonarQube Server') {
                     sh 'mvn clean package sonar:sonar'
                  }
              }
          }

          stage("Quality Gate"){
              timeout(time: 1, unit: 'HOURS') {
                  def qg = waitForQualityGate()
                  if (qg.status != 'OK') {
                      error "Pipeline aborted due to quality gate failure: ${qg.status}"
                  }
              }
          }
       
        }
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
    }
}
