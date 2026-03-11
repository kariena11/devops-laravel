pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                // Menggunakan cp karena rsync tidak terinstall di Jenkins
                sh 'cp -r . /home/kariena/devops-laravel/prod'
            }
        }
    }
}
