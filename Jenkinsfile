pipeline{
    agent any
    stages{
        stage("Restoring dependencies"){
            when {
                expression {
                    return env.GIT_BRANCH == "origin/main"
                }
            }
            steps{
                sh "dotnet restore"
            }
        }
        stage("Building project"){
            when {
                expression {
                    return env.GIT_BRANCH == "origin/main"
                }
            }
            steps{
                sh "dotnet build --no-restore"
            }
        }
        stage("Running tests"){
            when {
                expression {
                    return env.GIT_BRANCH == "origin/main"
                }
            }
            steps{
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
}