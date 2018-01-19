pipeline {
  agent any
  stages {
    stage('Production') {
      steps {
        dir(path: './gameoflife-ansible') {
          ansiblePlaybook '*/gameoflife-ansible/production.yml'
        }
        
      }
    }
  }
}