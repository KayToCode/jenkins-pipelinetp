pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Utilisation du chemin complet vers gradle.exe
                bat '"C:\\Program Files\\gradle-9.2.0\\bin\\gradle.exe" build'
            }
        }

        stage('Test') {
            steps {
                // Lancer les tests avec Gradle
                bat '"C:\\Program Files\\gradle-9.2.0\\bin\\gradle.exe" check'
            }
        }
    }

    post {
        always {
            // Enregistre les fichiers JUnit générés pour Jenkins
            junit 'build/test-results/test/*.xml'

            // Archive les fichiers produits (artefacts)
            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
        }
    }
}
