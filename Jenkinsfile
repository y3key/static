pipeline {
  agent any
  
  stages {
    
    stage('Upload to AWS') {
        steps {
            echo 'Deploying to aws...'
            withAWS(region:'us-east-2',credentials:'aws-static')
            {
                s3Upload(file: 'index.html', bucket: 'friesecicd', path: '')
            }
        }
    }
    
  }
}
