pipeline {
    stages {
         
        stage('build') {
            agent { docker { image 'python:3.5.1' } }
            steps {
                sh 'python test1.py'
            }
        }
    }
}
