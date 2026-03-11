pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                // Langsung kirim file tanpa proses build di Jenkins
                sh 'rsync -avz --exclude=".git" . /home/kariena/devops-laravel/prod'
            }
        }
    }
}
