pipeline {
  agent any
  stages {
    stage('version') {
      steps {
        sh 'python3 --version'
      }
    }
    stage('Execution!') {
      steps {
        sh 'python3 hello.py'
      }
    }
    stage('Generate Report') {
      steps {
        sh 'python3 generateReport.py'
      }
    }
  }
}
