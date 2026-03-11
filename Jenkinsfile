pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                // Kita abaikan composer di dalam Jenkins karena container-mu minimalis
                echo 'Skipping composer inside Jenkins container...'
            }
        }
        stage('Deploy to Prod') {
            steps {
                // Kita copy file ke folder yang bisa diakses Jenkins
                // Lalu kita sinkronkan ke folder prod di server
                sh '''
                cp -r . /var/jenkins_home/workspace/laravel-dev-deploy
                sudo cp -r /var/jenkins_home/workspace/laravel-dev/. /home/kariena/devops-laravel/prod/
                '''
            }
        }
    }
}
