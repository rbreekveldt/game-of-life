pipeline {
  agent any
  stages {
    stage('Production') {
      steps {
        dir(path: './gameoflife-ansible') {
          ansiblePlaybook '/usr/local/bin/ansible-playbook'
        }
        
      }
    }
  }
}