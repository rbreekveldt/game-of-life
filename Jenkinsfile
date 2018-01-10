pipeline {
  agent any
  stages {
    stage('Production') {
      steps {
        sh 'ls'
        sh 'pwd'
        dir(path: './gameoflife-ansible') {
          sh 'ls'
          sh 'pwd'
          ansiblePlaybook(playbook: 'acceptance.yml')
        }
        
      }
    }
  }
}