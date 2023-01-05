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
        sh 'dotnet restore Solution1/Solution1.sln'
        sh 'ls -la'
      }
    }

    stage('build') {
      steps {
        sh 'docker build -f authwebapi/dockerfile .'
      }
    }

  }
}