pipeline {
    //Use the following docker image to run your dotnet app.
    agent { docker { image 'gfoidl/dotnet-mono:2.1-sdk-5.12.0.226' } }
    environment {HOME = '/tmp'} 
    stages {
    // Get some code from a GitHub repository
    stage('Git') {
      steps{
          git 'https://github.com/ItayFrid/SocialNetwork.git'
      }
   }
    stage('Dotnet Restore'){
        steps{
        sh "dotnet restore --configfile SocialNetwork/packages.config"
        }
    }
    
   stage('Build'){
          steps{
               sh "dotnet build SocialNetwork.sln"
               }
    }
    stage('Run Tests'){
          steps{
               sh "dotnet test"
          }
    }
}
}
