@'
pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Récupération du code') {
            steps {
                checkout scm
            }
        }
        stage('Date système') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'date'
                    } else {
                        bat 'date /t && time /t'
                    }
                }
            }
        }
    }
}
'@ | Set-Content -Encoding UTF8 .\Jenkinsfile

git add Jenkinsfile
git commit -m "Fix Jenkinsfile compatible Windows"
git push origin main