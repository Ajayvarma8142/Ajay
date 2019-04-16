pipeline {
  agent any
   tools { 
        maven 'maven' 
	      jdk 'jdk'
	      git 'git'
        
    }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/Ajayvarma8142/Ajay.git'
      }
    }
    stage('build') {
      steps {
        bat 'mvn install'
      }
    }
  }
}
