pipeline {
  agent any
  stages {
    stage('UploadtoAWS') {
      steps {
        withAWS(region:'us-east-1', credentials:'aws-static') {
          s3Upload(file:'index.html', bucket:'smiddleycicd', path:'https://friesecicd.s3.amazonaws.com/index.html')
      }
    }
  }
}
