pipeline {
  agent any
  stages {
    stage('Run integration tests ') {
      steps {
        dir(path: './gameoflife-ansible') {
          ansiblePlaybook(playbook: 'acceptance.yml')
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