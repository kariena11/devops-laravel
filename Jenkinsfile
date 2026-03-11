pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Menjalankan composer tanpa docker
                sh 'composer install --no-interaction --prefer-dist --optimize-autoloader'
            }
        }
        stage('Deploy') {
            steps {
                // Mengirim file ke folder prod
                sh 'rsync -avz --exclude=".git" . /home/kariena/devops-laravel/prod'
            }
        }
    }
}
