pipeline {
  agent any
  stages {
    stage('code pull') {
      steps {
        git(url: 'https://github.com/Ajayvarma8142/Ajay.git', branch: 'master')
      }
    }
    stage('build') {
      steps {
        bat '#bin/bash!'
      }
    }
    stage('test') {
      steps {
        bat 'mvn test'
      }
    }
    stage('deploy') {
      steps {
        bat '#!test'
      }
    }
  }
}