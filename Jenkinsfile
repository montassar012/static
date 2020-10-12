pipeline {
  agent any
  stages {
    stage('Lint HTML.') {
      steps {
                sh 'echo Linting HTML'
                sh 'tidy -q -e *.html'
            }
    }
    stage('Upload to AWS.') {
      steps {
        withAWS(region:'us-east-1',credentials: 'aws-static') {
          s3Upload(file: 'index.html', bucket:'udacity-jenkins-static-mk', path:'index.html')
        }
      }
    }

  }
}
