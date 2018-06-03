pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'git@github.com:LetTheAwesomeBegin/Jenkins-Sample.git', branch: 'master', changelog: true, poll: true)
      }
    }
    stage('Build') {
      steps {
        sh './gradlew clean assemble'
      }
    }
  }
  environment {
    ENV = 'DEV'
  }
}