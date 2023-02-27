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
        sh '/Library/Developer/CommandLineTools/usr/bin/python3 -m pip install pytest'
        sh '/Library/Developer/CommandLineTools/usr/bin/python3 -m pip install pytest-html'
      }
    }
    stage('hello') {
      steps {
        sh '/Library/Developer/CommandLineTools/usr/bin/python3 -m pip install --upgrade pip'
        sh '/Library/Developer/CommandLineTools/usr/bin/python3 -m pip install webdriver_manager'
        sh '/Library/Developer/CommandLineTools/usr/bin/python3 -m pip install selenium'
        sh '/Library/Developer/CommandLineTools/usr/bin/python3 hello.py'
      }
    }
    stage('pytest'){
      steps{
//         sh '/opt/homebrew/bin/pytest --html=index.html --self-contained-html'
        sh '/opt/homebrew/bin/pytest test_suite.py --html=report/index.html --self-contained-html'
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '\\report\\', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
      }
    }
  }
}
