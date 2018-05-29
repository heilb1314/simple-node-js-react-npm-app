pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'sh \'npm install\''
      }
    }
    stage('Test') {
      steps {
        sh 'sh \'./jenkins/scripts/test.sh\''
      }
    }
    stage('Deliver') {
      steps {
        sh '''sh \'./jenkins/scripts/deliver.sh\'
input message: \'Finished using the web site? (Click "Proceed" to continue)\'
sh \'./jenkins/scripts/kill.sh\''''
      }
    }
  }
}