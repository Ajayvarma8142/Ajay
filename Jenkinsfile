pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/Ajayvarma8142/Ajay.git'
        echo 'code checkout sucessfully'
      }
    }
    stage('build') {
      steps {
        bat 'mvn install'
      }
    }
  }
}