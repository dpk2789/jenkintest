pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/dpk2789/jenkintest', branch: 'main')
      }
    }

    stage('build') {
      steps {
        sh 'dotnet build'
      }
    }

  }
}