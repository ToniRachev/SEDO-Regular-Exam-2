pipeline {
    agent any

    stages {
        stage('Checkout') {
            when { branch 'main' }
            steps {
                checkout scm
            }
        }
        stage('Restore Dependencies') {
            when { branch 'main' }
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            when { branch 'main' }
            steps {
                sh 'dotnet build --configuration Release --no-restore'
            }
        }
        stage('Test') {
            when { branch 'main' }
            steps {
                sh 'dotnet test --no-build --verbosity normal --configuration Release'
            }
        }
    }
}