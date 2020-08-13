pipeline {
  options {
    buildDiscarder(logRotator(numToKeepStr: '3', artifactNumToKeepStr: '3'))
  }
  triggers {
        pollSCM('*/30 * * * *')
  }
  agent any
  
  stages {
    stage('Compile') {
        steps {
           sh './mvnw clean compile'
        }
    }
    stage('Test  ') {
        steps {
           sh './mvnw test'
        }
    }
  }   
}
