pipeline {
  agent any
  stages {
    stage('Run integration tests ') {
      agent any
      steps {
        dir(path: './gameoflife-ansible') {
          ansiblePlaybook(playbook: 'acceptance.yml', extras: '-vvv', extraVars: '"export ANSIBLE_HOST_KEY_CHECKING=False"')
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