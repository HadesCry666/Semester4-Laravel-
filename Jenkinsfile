node {

    checkout scm

    stage("Build") {
        docker.image('composer:2.7').inside('-u root') {
            sh 'git config --global --add safe.directory /var/jenkins_home/workspace/Laravel'
            sh 'composer install'
        }
    }

    stage("Testing") {
        docker.image('ubuntu').inside('-u root') {
            sh 'echo "Ini adalah test"'
        }
    }

}