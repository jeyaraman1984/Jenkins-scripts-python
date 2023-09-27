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
    stage('Install libs!') {
      steps {
                sh '''
                    python3 -m pip install --upgrade pip
                    pip install xlsxwriter
                '''
            }
    }
    stage('Generate Report!') {
      steps {
        sh 'python3 generateReport.py'
      }
    }
  }
}
