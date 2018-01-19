pipeline {
  agent any
  stages {
    stage('Production') {
      steps {
        dir(path: '/usr/local/bin/') {
          ansiblePlaybook './gameoflife-ansible/production.yml'
        }
        
      }
    }
  }
}