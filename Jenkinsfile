pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'composer install'
      }
    }
    stage('Tests') {
      steps {
        sh './vendor/bin/phpunit'
      }
    }
    stage('Deploy') {
      steps {
        sh 'sudo rocketeer deploy'
      }
    }
  }
  triggers {
    pollSCM('* * * * *')
  }
}