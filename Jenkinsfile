pipeline {
    agent any

    stages {

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
    stage('Check .NET') {
    steps {
        sh 'dotnet --list-runtimes'
    }
}
}
