pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Compile le projet et construit les artefacts
                bat 'gradlew.bat build'
            }
        }

        stage('Test') {
            steps {
                // Lance les tests
                bat 'gradlew.bat check'
            }
        }
    }

    post {
        always {
            // Enregistre les fichiers JUnit générés pour Jenkins
            junit 'build/test-results/test/*.xml'

            // Archive les fichiers produits (artefacts) pour analyse ou téléchargement
            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
        }
    }
}
