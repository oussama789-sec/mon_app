pipeline {
    agent any

    environment {
        // Définit les variables d'environnement si nécessaire
        TOMCAT_USER = 'admin'
        TOMCAT_PASSWORD = 'motdepasse'
        TOMCAT_HOST = 'http://localhost:8080'
    }

    stages {
        stage('Checkout') {
            steps {
                // Récupère les sources depuis GitHub
                git branch: 'main', url: 'https://github.com/tonutilisateur/tonprojet.git'
            }
        }
        stage('Build') {
            steps {
                // Compile ton projet avec Maven
                script {
                    sh 'mvn clean install'
                }
            }
        }
        stage('Deploy') {
            steps {
                // Déploie sur Tomcat
                script {
                    sh 'mvn tomcat7:deploy'
                }
            }
        }
    }
}
