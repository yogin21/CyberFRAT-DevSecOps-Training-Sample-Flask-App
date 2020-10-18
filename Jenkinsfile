pipeline {
  environment {
    registry = "yogin2004/yogindevops"
    registryCredential = "DockerHub"
    dockerImage = ''
  }
  
  agent any
  
  stages {
    stage('Build Docker Image') {
      steps {
        script {
          dokcerImage = docker.build registry + ":$BUILD_NUMBER"
         }
      }
    }
    
    stage('Push to DockerHub') {
      steps {
        script {
        docker.withRegistry('', registryCredential ) {
          dockerImage.push()
        }
      }
    }
  }
    
    stage('Test Run') {
      steps {
        sh 'docker run -d $registry:$BUILD_NUMBER'
      }
    }
   }
  } 
