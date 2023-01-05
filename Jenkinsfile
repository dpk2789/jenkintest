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
        sh 'dotnet restore Solution1/AuthWebApi/AuthWebApi.csproj'
        sh 'ls -la'
      }
    }

    stage('build') {
      steps {
        sh 'docker build -t shadesofweb/webapi3:v0.${BUILD_NUMBER} -f Solution1/AuthWebApi/Dockerfile .'
      }
    }

    stage('login docker and push') {
      steps {
        sh '''docker login -u shadesofweb -p Password#1
docker push shadesofweb/webapi3:v0.${BUILD_NUMBER}'''
      }
    }

  }
}