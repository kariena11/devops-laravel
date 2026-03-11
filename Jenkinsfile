node {
    checkout scm
    stage("Build") {
    steps {
        sh 'composer install'
        }
    }
    stage("Testing") {
        docker.image('ubuntu').inside('-u root') {
            sh 'echo "Testing Berhasil"'
        }
    }
    stage("Deploy to Prod") {
        docker.image('agung3wi/alpine-rsync:1.1').inside('-u root') {
            sshagent (credentials: ['ssh-server-key']) {
                sh 'mkdir -p ~/.ssh'
                sh 'ssh-keyscan -H "$PROD_HOST" >> ~/.ssh/known_hosts'
                sh "rsync -rav --delete ./ root@${PROD_HOST}:/home/kariena/devops-laravel/prod/ --exclude=.env --exclude=storage --exclude=.git"
            }
        }
    }
}
