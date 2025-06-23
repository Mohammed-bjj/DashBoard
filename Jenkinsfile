pipeline {
    agent any

 
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Mohammed-bjj/DashBoard.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        
        stage('Deploy') {
            steps {
                // Adaptez cette partie selon votre méthode de déploiement
                // Exemple: copie vers un serveur, déploiement sur Firebase, etc.
                sh 'echo "Déploiement de l\'application"'
                // sh 'scp -r dist/ user@server:/path/to/destination'
            }
        }
    }
    
    post {
        always {
            cleanWs() // Nettoyer l'espace de travail
        }
    }
}