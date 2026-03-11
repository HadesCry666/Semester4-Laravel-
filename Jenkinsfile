node {

    checkout scm

    stage("Build") {
        docker.image('composer:2.7').inside('--entrypoint="" -u root') {
            sh 'composer install --no-scripts'
        }
    }

    stage("Testing") {
        docker.image('php:8.1-cli').inside('-u root') {
            sh 'php -v'
        }
    }

    stage("Deploy Production") {
        docker.image('agung3wi/alpine-rsync:1.1').inside('-u root') {

            sshagent (credentials: ['ssh-jenkins']) {

                sh '''
                mkdir -p ~/.ssh
                ssh-keyscan -H $PROD_HOST >> ~/.ssh/known_hosts

                rsync -rav --delete ./ \
                ubuntu@$PROD_HOST:/home/ubuntu/prod.kelasdevops.xyz/ \
                --exclude=.env \
                --exclude=storage \
                --exclude=.git
                '''
            }
        }
    }

}