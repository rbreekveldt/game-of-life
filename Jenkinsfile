pipeline {
  agent any
  stages {
    stage('Run integration tests ') {
      agent {
        node {
          label 'ansiblePlaybook'
        }
        
      }
      steps {
        dir(path: './gameoflife-ansible') {
          ansiblePlaybook(playbook: 'acceptance.yml', extras: '-vvv')
        }
        
      }
    }
    stage('Production') {
      steps {
        dir(path: './gameoflife-ansible') {
          ansiblePlaybook(playbook: 'production.yml')
        }
        
      }
    }
  }
}