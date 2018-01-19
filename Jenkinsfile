pipeline {
  agent any
  stages {
    stage('Production') {
      steps {
        dir(path: './gameoflife-ansible') {
          sh 'ls'
          sh 'ansible-playbook production.yml'
          ansiblePlaybook(playbook: 'production.yml', installation: '*/usr/local/bin/ansible-playbook', extras: 'export ANSIBLE_HOST_KEY_CHECKING=False')
        }
        
      }
    }
  }
}