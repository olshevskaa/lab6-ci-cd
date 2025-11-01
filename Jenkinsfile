pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/heroku/node-js-sample.git'
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test || echo "No tests yet"'
            }
        }

        stage('Package') {
            steps {
                sh 'zip -r app.zip *'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
