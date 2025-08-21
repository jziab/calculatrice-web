pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Compilation du projet...'
                echo 'Packaging en cours...'
            }
        }

        stage('Test') {
            steps {
                // Check if index.html exists
                bat '''
                if exist index.html (
                    echo 'Le fichier index.html existe.'
                ) else (
                    echo 'ERREUR: index.html manquant'
                    exit /b 1
                )
                '''
            }
        }

    }

    post {
        success {
            echo 'Pipeline terminé avec succès ! 🎉'
        }
        failure {
            echo 'Pipeline échoué ❌ - vérifier les logs.'
        }
        always {
            echo 'Fin du pipeline - nettoyage global si nécessaire.'
        }
    }
}
