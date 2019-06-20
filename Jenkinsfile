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
        bat 'rem testbuild'
      }
    }
    stage('test') {
      steps {
        bat 'mvn test'
      }
    }
    stage('deploy') {
      steps {
        bat 'rem test'
      }
    }
  }
}