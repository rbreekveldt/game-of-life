pipeline {
  agent any
  stages {
    stage('Run integration tests ') {
      steps {
        dir(path: './gameoflife-ansible') {
          ansiblePlaybook(playbook: 'acceptance.yml')
          sh 'debug info'
        }
        
      }
    }
    stage('Production') {
      steps {
        dir(path: 'gameoflife-ansible/') {
          ansiblePlaybook(playbook: 'production.yml')
        }
        
      }
    }
  }
}