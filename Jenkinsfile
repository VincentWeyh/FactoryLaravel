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
        sh 'rocketeer deploy'
      }
    }
    stage('Start server') {
      steps {
        sh 'php artisan serve --host 0.0.0.0'
      }
    }
  }
}