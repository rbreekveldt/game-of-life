pipeline {
  agent any
  stages {
    stage('Deploy') {
      steps {
        withMaven(globalMavenSettingsConfig: 'cbe36984-77a3-45e6-945a-b7d24dda9751') {
          sh 'mvn clean deploy'
        }
        
      }
    }
    stage('Build and run unit test') {
      steps {
        sh 'mvn clean package'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Release') {
      steps {
        withMaven(globalMavenSettingsConfig: 'cbe36984-77a3-45e6-945a-b7d24dda9751') {
          sh 'mvn -Dresume=false release:prepare release:perform'
        }
        
      }
    }
    stage('Run integration tests ') {
      steps {
        dir(path: 'gameoflife-ansible/') {
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