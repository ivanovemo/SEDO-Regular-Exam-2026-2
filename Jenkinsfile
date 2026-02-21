pipeline{
    agent any
    stages{
        stage("Restoring dependencies"){
            when {
                branch "main"
            }
            steps{
                sh "dotnet restore"
            }
        }
        stage("Building project"){
            when {
                branch "main"
            }
            steps{
                sh "dotnet build --no-restore"
            }
        }
        stage("Running tests"){
            when {
                branch "main"
            }
            steps{
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
}