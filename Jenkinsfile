pipeline {
  agent any
  triggers{
    poolSCM('* * * * *')
  }
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
        sh 'rocketeer deploy'
      }
    }
  }
}
