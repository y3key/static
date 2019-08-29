pipeline {
  agent any
  
  stages {
    
    stage('Lint HTML') {
        steps {
            echo 'Static Code Check...'
            sh '''
              cp index.html /home/ubuntu/lintcheck
              cd /home/ubuntu/lintcheck
              tidy -q -e *.html
            '''
        }
    }
    
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
