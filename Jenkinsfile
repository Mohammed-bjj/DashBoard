pipeline {
    agent any

    tools {
        nodejs "node" // Le nom que vous avez donné à votre installation Node.js
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Mohammed-bjj/DashBoard.git'
            }
        }
        
        stage('Run Ansible for Dependencies and Build') {
            steps {
                // Exécution des tâches Ansible pour installer les dépendances et builder
                ansiblePlaybook(
                    playbook: 'ansible/run/install_build.yml', // Chemin vers votre playbook Ansible
                    inventory: 'ansible/inventory/inventory.ini',   // Chemin vers votre inventaire
                    credentialsId: '' // ID des credentials si nécessaire
                )
            }
        }
        
        stage('Deploy') {
            steps {
                // Adaptez cette partie selon votre méthode de déploiement
                // Exemple: copie vers un serveur, déploiement sur Firebase, etc.
                sh 'echo " ss Déploiement de l\'application"'
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