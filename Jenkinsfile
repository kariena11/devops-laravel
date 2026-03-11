pipeline {
    agent any 

    stages {
        // Stage Checkout otomatis sudah dilakukan oleh Jenkins di awal
        
        stage('Install Dependencies') {
    steps {
        sh '''
            # Download composer.phar secara lokal di folder project
            curl -sS https://getcomposer.org/installer | php
            
            # Jalankan instalasi menggunakan php langsung ke file .phar tadi
            php composer.phar install --no-interaction --prefer-dist
        '''
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
