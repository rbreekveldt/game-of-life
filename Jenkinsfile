pipeline {
  agent any
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