
pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Récupération du code source') {
            steps {
                checkout scm
            }
        }

        stage('Affichage de la date système') {
            steps {
                sh 'date'
            }
        }
    }
}
