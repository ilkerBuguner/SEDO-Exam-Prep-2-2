pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            when {
                expression {
                    return env.BRANCH_NAME == 'origin/main'
                }
            }
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build the app') {
            when {
                expression {
                    return env.BRANCH_NAME == 'origin/main'
                }
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run the tests') {
            when {
                expression {
                    return env.BRANCH_NAME == 'origin/main'
                }
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}