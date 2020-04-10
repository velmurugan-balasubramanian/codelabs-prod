#!groovy

def uploadAndInvalidate(environment) {
  def s3Path = "/codelabs"

  def STATIC_ASSETS = [
    staging: [
      bucketName: 'codelabs-prod',
      profile: 'default'
    ]
  ]

  uploadAssetsToS3('dist', "s3://${STATIC_ASSETS[environment].bucketName}${s3Path}", 'us-east-1', true, false, 86400, STATIC_ASSETS[environment].profile)

}

pipeline {
    agent any
    stages {
        stage('upload to s3') {
            steps {
                uploadAndInvalidate('staging');
            }
        }
    }
}
