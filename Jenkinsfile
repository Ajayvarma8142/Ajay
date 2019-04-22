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
            bat 'mvn sonar:sonar'
          }
        }
      }
    }
    stage('Artifactory') {
      steps {
        bat ' web.xml'
      }
    }
  }
}
