pipeline {
  agent any
  stages {
    stage('Production') {
      steps {
        dir(path: './gameoflife-ansible') {
          sh 'ls'
          sh 'pwd'
          ansiblePlaybook(playbook: 'production.yml', installation: '/usr/local/bin/')
        }
        
      }
    }
  }
}