pipeline {
  agent {
    dockerfile {
      filename '*/gameoflife-web/Dockerfile'
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