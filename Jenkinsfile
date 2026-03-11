pipeline {
    agent any 

    stages {
        // Stage Checkout otomatis sudah dilakukan oleh Jenkins di awal
        
        stage('Install Dependencies') {
            steps {
                // Gunakan perintah sh biasa
                sh 'composer install --no-interaction --prefer-dist'
            }
        }

        stage('Build & Test') {
            steps {
                sh 'cp .env.example .env'
                sh 'php artisan key:generate'
                // Tambahkan perintah testing jika ada, misal: ./vendor/bin/phpunit
            }
        }
    }
}
