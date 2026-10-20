pipeline {
    agent any

    triggers {
        githubPush()   // déclenché par le webhook GitHub
        // alternative sans webhook : pollSCM('* * * * *')
    }

    stages {
        stage('Récupération du code') {
            steps {
                git branch: 'main', url: 'https://github.com/YONATHANK2403/Projet_JEE.git'
            }
        }
        stage('Date système') {
            steps {
                sh 'date'
            }
        }
    }
}