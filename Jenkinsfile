#!groovy

def uploadAndInvalidate() {
  def s3Path = "/"

  uploadAssetsToS3('dist', "s3://codelabs-prod", 'us-east-1', true, false, 86400, 'prod')

}

pipeline {
    agent any
    stages {
        stage('upload to s3') {
            steps {
                uploadAndInvalidate();
            }
        }
    }
}
