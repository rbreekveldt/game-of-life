pipeline {
  agent {
    docker {
      image 'tomcat:8-jre8'
      args '-p 4000:8080'
    }
    
  }
  stages {
    stage('Initialize') {
      steps {
        sh 'mvn clean '
      }
    }
    stage('Build') {
      steps {
        sh 'mvn install'
      }
    }
    stage('Report') {
      steps {
        junit '**/reports/*.xml'
      }
    }
  }
}