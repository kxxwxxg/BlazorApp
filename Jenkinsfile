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
        sh 'sudo python3 -m pip install pytest'
        sh 'sudo python3 -m pip install pytest-html'
      }
    }
    stage('hello') {
      steps {
        sh '/Library/Developer/CommandLineTools/usr/bin/python3 -m pip install --upgrade pip'
        sh 'python3 -m pip install webdriver_manager'
        sh 'python3 -m pip install selenium'
        sh 'python3 hello.py'
      }
    }
    stage('pytest'){
      steps{
        sh 'pytest --version'
//         sh 'pytest --html=report.html --self-contained-html'
      }
    }
  }
}
