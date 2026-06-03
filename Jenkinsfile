pipeline {
    agent any

    stages {
        stage('Vérifier Nouveau Commit') {
            steps {
                echo 'Vérification des nouveaux commits dans main...'
                sh 'git fetch origin'
                sh 'git checkout main'
                sh 'git log -1 --format=%H origin/main > /tmp/latest_commit.txt'
            }
        }

        stage('Déployer') {
            steps {
                echo 'Déploiement en cours...'
                sh 'git pull origin main'
                sh 'echo "Déploiement effectué avec succès"'
            }
        }
    }
}
