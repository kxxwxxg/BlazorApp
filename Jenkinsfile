pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '/opt/homebrew/bin/dotnet build'
      }
    }
    stage('version') {
      steps {
        sh 'printenv'
      }
    }
    stage('hello') {
      steps {
        sh 'python3 hello.py'
      }
    }
  }
}
