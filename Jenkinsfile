pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Skipping composer inside Jenkins container...'
            }
        }
        stage('Deploy to Prod') {
            steps {
                // Hapus sudo karena di dalam container tidak ada sudo
                sh '''
                cp -rv . /home/kariena/devops-laravel/prod/
                '''
            }
        }
    }
}
