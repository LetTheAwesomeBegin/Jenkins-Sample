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
        echo 'API compatibility check'
      }
    }
    stage('Test') {
      parallel {
        stage('Test Network 1') {
          steps {
            echo 'Deploy to test'
            echo 'Test on test'
            echo 'Deploy to test latest prod version'
            echo 'Test on test latest prod version'
          }
        }
        stage('Test Network 2') {
          steps {
            echo 'Deploy to test'
            echo 'Test on test'
            echo 'Deploy to test latest prod version'
            echo 'Test on test latest prod version'
          }
        }
      }
    }
  }
  environment {
    ENV = 'DEV'
  }
}