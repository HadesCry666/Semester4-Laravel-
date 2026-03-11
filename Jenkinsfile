node {

    checkout scm

    // Build
    stage("Build") {
        docker.image('composer:2').inside('-u root') {
            sh 'composer install'
        }
    }

    // Testing
    stage("Testing") {
        docker.image('ubuntu').inside('-u root') {
            sh 'echo "Ini adalah test"'
        }
    }

}