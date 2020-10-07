#!groovy

def uploadAndInvalidate() {
  def s3Path = "/codelabs"

  uploadAssetsToS3('dist', "s3://codelabs-prod/tutorials", 'us-east-1', true, false, 86400, 'prod');
  invalidateCDN('E2OJAP80EGS5J2', '\"/*\"', 'prod');


}

pipeline {
    agent any
    stages {
        stage('upload to s3') {
            steps {
              sh 'echo COMMAND RUNS HERE'
              sh 'apt-get install python-software-properties'
              sh 'add-apt-repository ppa:duh/golang'
              sh 'apt-get update'
              sh 'apt-get install golang'
              sh 'mv go /usr/local'
              sh 'export GOROOT=/usr/local/go'
              sh 'export GOPATH=$HOME/Projects/Proj1'
              sh 'export PATH=$GOPATH/bin:$GOROOT/bin:$PATH'
              sh 'go version'
                //uploadAndInvalidate();
            }
        }
    }
}
