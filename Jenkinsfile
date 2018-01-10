pipeline {
  agent any
  stages {
    stage('Production') {
      steps {
        dir(path: './gameoflife-ansible') {
          sh 'ls'
          sh 'pwd'
          ansiblePlaybook(playbook: 'acceptance.yml')
        }
        
      }
    }
  }
}