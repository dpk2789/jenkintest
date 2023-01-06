pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/dpk2789/jenkintest', branch: 'main')
      }
    }

    stage('restore') {
      steps {
        sh '''dotnet restore Solution1/webapi.aowproducts/webapi.aowproducts.csproj
dotnet publish -c release Solution1/Solution1.sln'''
        sh 'ls -la'
      }
    }

    stage('build') {
      steps {
        sh 'docker build -t shadesofweb/webapi4:v0.${BUILD_NUMBER} -f Solution1/webapi.aowproducts/Dockerfile .'
      }
    }

    stage('login docker and push') {
      steps {
        sh '''docker login -u shadesofweb -p Password#1
docker push shadesofweb/webapi4:v0.${BUILD_NUMBER}'''
      }
    }

  }
}