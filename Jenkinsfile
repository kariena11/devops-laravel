pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/kariena11/devops-laravel.git'
            }
        }

        stage('Install') {
            steps {
                sh 'composer install'
            }
        }

        stage('Build') {
            steps {
                sh 'php artisan config:cache'
            }
        }
    }
}
