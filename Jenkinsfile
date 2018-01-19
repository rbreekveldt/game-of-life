pipeline {
  agent any
  stages {
    stage('Production') {
      steps {
        dir(path: 'gameoflife-ansible') {
          fileExists 'production.yml'
          ansiblePlaybook(playbook: 'production.yml', sudo: true, sudoUser: 'jenkins')
        }
        
      }
    }
  }
}