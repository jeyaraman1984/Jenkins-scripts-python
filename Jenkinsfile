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
    //stage('Upload to S3') {
    //  steps {
    //    script {
          // Define your AWS S3 bucket name and report file name
    //      def s3Bucket = 'your-s3-bucket-name'
    //      def reportFile = 'report.xlsx'

          // Use the AWS CLI to upload the report to S3
    //      sh "aws s3 cp ${reportFile} s3://${s3Bucket}/${reportFile}"
    //    }
    //  }
   // }
  }
  post {
    always {
      // Archive the generated Excel report as a build artifact.
      archiveArtifacts artifacts: 'report.xlsx', allowEmptyArchive: true
    }
  }
}
