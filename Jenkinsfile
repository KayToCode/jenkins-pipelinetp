pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                bat './gradlew.bat check'
            }
        }
    }
    post {
        always {
            junit 'build/reports/test/test1.xml'
        }
    }
}
