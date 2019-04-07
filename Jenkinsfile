pipeline {
  agent any
  stages {
    stage('code pull') {
      steps {
        git 'https://github.com/Ajayvarma8142/os-sample-java-web.git'
        echo 'Git checkout complete'
      }
    }
    stage('build') {
      steps {
        bat 'mvn clean install'
      }
    }
    stage('test') {
      parallel {
        stage('code analyze') {
          steps {
            withSonarQubeEnv('SonarQube') {
              bat 'mvn sonar:sonar'
            }

          }
        }
        stage('unit tests') {
          steps {
            bat 'mvn test'
          }
        }
      }
    }
    stage('dev-deploy') {
      steps {
        script {
          mvn tomcat8:deploy
        }

      }
    }
  }
  tools {
    maven 'maven'
    jdk 'jdk'
    git 'git'
  }
  options {
    skipDefaultCheckout(true)
  }
}