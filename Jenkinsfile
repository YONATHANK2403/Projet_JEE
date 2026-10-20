pipeline {
    agent any

    tools {
        // Nom des outils configurés dans l'étape 2 (à adapter selon vos labels Jenkins)
        jdk 'JDK-17'
        maven 'Maven-3'
    }

    stages {
        stage('1. Checkout Code') {
            steps {
                // Récupération du code source depuis GitHub
                git branch: 'main', url: 'https://github.com/YONATHANK2403/Projet_JEE.git'
            }
        }

        stage('2. Build & Test') {
            steps {
                // Exécution de la compilation Maven et des tests unitaires
                sh 'mvn clean package'
            }
        }

        stage('3. Analyse / Quality Check') {
            steps {
                // Étape réservée pour des analyses statiques (ex: SonarQube) si besoin
                echo "Analyse du code source en cours..."
            }
        }
    }

    post {
        success {
            echo 'Pipeline exécuté avec succès ! Le livrable (JAR/WAR) est prêt.'
        }
        failure {
            echo 'Échec lors de l\'exécution du pipeline. Veuillez vérifier les logs.'
        }
        always {
            // Nettoyage optionnel de l'espace de travail
            cleanWs()
        }
    }
}