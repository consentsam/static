pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        sh 'tidy -q -e *.html'
      }
    }

    stage('Upload to AWS.') {
      steps {
        sh 'echo "Hello World"'
        withAWS(credentials: 'aws-static', region: 'us-east-2') {
          s3Upload(bucket: 'jenkins-pipelines-on-aws-udacity-new', file: 'index.html')
        }

      }
    }

  }
}