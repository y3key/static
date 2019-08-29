pipeline {
  agent any
  stages {
    stage('UploadtoAWS') {
      steps {
        withAWS(region:'us-east-2', credentials:'aws-static') {
          s3Upload(file:'index.html', bucket:'friesecicd', path:'https://friesecicd.s3.amazonaws.com/index.html')
      }
    }
  }
}
