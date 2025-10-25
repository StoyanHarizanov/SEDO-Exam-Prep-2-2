pipeline {
    agent any

    stages {

        stage('Check .NET') {
            steps {
                echo 'Checking installed .NET runtimes...'
                sh 'dotnet --list-runtimes'
            }
        }

        stage('Build .NET Project') {
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
}
