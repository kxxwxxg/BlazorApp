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
        sh 'python3 -m pip install selenium'
      }
    }
    stage('hello') {
      steps {
        sh 'whoami'
        sh 'python3 hello.py'
      }
    }
  }
}
