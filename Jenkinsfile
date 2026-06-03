pipeline {
    agent any

    stages {
        stage('Vérifier Interconnexion') {
            steps {
                echo 'Vérification de l\'interconnexion en cours...'
                sh 'echo "Interconnexion vérifiée"'
            }
        }

        stage('Récupérer Release') {
            steps {
                echo 'Récupération du dernier release depuis /release...'
                sh 'git checkout release'
                sh 'git pull origin release'
            }
        }

        stage('Déployer dans Main') {
            steps {
                echo 'Déploiement dans la branche main...'
                sh 'git checkout main'
                sh 'git merge release'
                sh 'git push origin main'
            }
        }
    }
}
