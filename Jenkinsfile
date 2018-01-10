pipeline {
  agent any
  stages {
    stage('Run integration tests ') {
      steps {
        dir(path: './gameoflife-ansible') {
          ansiblePlaybook(playbook: './gameoflife-ansible/acceptance.yml', extras: '-vvv')
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