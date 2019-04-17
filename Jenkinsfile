pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/Ajayvarma8142/Ajay.git'
      }
    }
    stage('build') {
      parallel {
        stage('build') {
          steps {
            bat(script: 'mvn clean install', returnStatus: true)
          }
        }
        stage('SonarQube') {
          steps {
            bat 'mvn sonar:sonar \\   -Dsonar.projectKey=ajay \\   -Dsonar.host.url=http://localhost:9000 \\   -Dsonar.login=d474b4b2d6527baf778bc4ce5a28d469590118e2'
          }
        }
      }
    }
  }
}