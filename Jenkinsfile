pipeline {
  agent any
  
  stages {
    
    stage('Lint HTML') {
        steps {
            echo 'Static Code Check...'
            sh 'cd /home/ubuntu'
            sh 'pwd'
            sh 'ls -lh'
            sh 'tidy -q -e *.html'
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
