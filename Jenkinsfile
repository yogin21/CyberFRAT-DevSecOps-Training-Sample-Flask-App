pipeline {
  agent any
  
  stages {
    stage('Build Docker Image') {
      steps {
        sh 'docker build -t yogicyberfrat:$BUILD_NUMBER .'
        }
      }
    stage('Test Run') {
      steps {
        sh 'docker run -d yogicyberfrat:$BUILD_NUMBER'
      }
    }
   }
  } 
