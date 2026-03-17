pipeline {
    agent any

    environment {
        PROD_USER = "ubuntu"
        PROD_PATH = "/home/ubuntu/prod.kelasdevops.xyz"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build - Composer Install') {
            steps {
                script {
                    docker.image('composer:2.7').inside('--entrypoint="" -u root') {
                        sh '''
                            composer install \
                              --no-interaction \
                              --prefer-dist \
                              --optimize-autoloader \
                              --no-dev \
                              --no-scripts
                        '''
                    }
                }
            }
        }

        stage('Testing - PHP Check') {
            steps {
                script {
                    docker.image('php:8.1-cli').inside('-u root') {
                        sh 'php -v'
                    }
                }
            }
        }

        stage('Deploy Production') {
            when {
                expression { return env.PROD_HOST?.trim() }
            }

            steps {
                script {
                    docker.image('agung3wi/alpine-rsync:1.1').inside('-u root') {

                        sshagent(credentials: ['ssh-jenkins']) {

                            sh '''
                                echo "=== Deploy ke $PROD_HOST ==="

                                mkdir -p ~/.ssh
                                chmod 700 ~/.ssh

                                # Add host key biar tidak prompt
                                ssh-keyscan -H $PROD_HOST >> ~/.ssh/known_hosts 2>/dev/null || true

                                # Sync file ke server
                                rsync -az --delete ./ \
                                  $PROD_USER@$PROD_HOST:$PROD_PATH \
                                  --exclude=.env \
                                  --exclude=storage \
                                  --exclude=.git

                                echo "=== Optimize Laravel ==="

                                ssh $PROD_USER@$PROD_HOST << 'EOF'
                                    cd /home/ubuntu/prod.kelasdevops.xyz
                                    php artisan config:cache || true
                                    php artisan route:cache || true
                                    php artisan view:cache || true
                                EOF

                                echo "=== Deploy selesai ==="
                            '''
                        }
                    }
                }
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline SUCCESS'
        }
        failure {
            echo '❌ Pipeline FAILED'
        }
    }
}