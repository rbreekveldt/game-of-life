pipeline {
  agent any
  stages {
    stage('Run integration tests ') {
      agent any
      steps {
        ansiblePlaybook(playbook: './gameoflife-ansible/acceptance.yml')
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