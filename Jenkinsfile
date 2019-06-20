pipeline {
  agent any
  stages {
    stage('code pull') {
      steps {
        git(url: 'https://github.com/Ajayvarma8142/Ajay.git', branch: 'master')
      }
    }
    stage('compile') {
      parallel {
        stage('compile') {
          steps {
            bat 'mvn compile'
          }
        }
        stage('Juni-test') {
          steps {
            bat 'mvn test'
          }
        }
      }
    }
    stage('build') {
      steps {
        bat 'mvn package'
      }
    }
    stage('deploy') {
      steps {
        bat 'rem test'
      }
    }
  }
}