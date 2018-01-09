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
        sh 'mvn -Dmaven.test.failure.ignore=true install'
      }
    }
    stage('Report') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
  }
}