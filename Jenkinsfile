pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out Repo 2...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'dotnet build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'dotnet test --no-build --logger "trx;LogFileName=TestResults.trx"'
            }
        }
    }

    post {
        always {
            echo 'Archiving test results...'
            junit '**/TestResults/*.trx'
        }
        success {
            echo 'Build and tests succeeded!'
        }
        failure {
            echo 'Build or tests failed!'
        }
    }
}
