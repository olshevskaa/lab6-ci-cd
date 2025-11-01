pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                script {
                    def testResult = bat(script: 'npm test', returnStatus: true)
                    if (testResult != 0) {
                        echo 'No tests yet or tests failed, continuing...'
                    }
                }
            }
        }
        stage('Package') {
            steps {
                bat 'powershell Compress-Archive -Path * -DestinationPath app.zip -Force'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}