node {

    checkout scm

    stage("Build") {
        docker.image('composer:2.7').inside('-u root') {
            sh 'composer install --no-scripts'
        }
    }

    stage("Testing") {
        docker.image('php:8.1-cli').inside('-u root') {
            sh 'php -v'
        }
    }

}