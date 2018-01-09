pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        sh 'mvn clean '
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
    stage('Run integration tests') {
      steps {
        dir(path: 'gameoflife-ansible/') {
          sh 'ansible-playbook acceptance.yml'
        }
        
      }
    }
    stage('Deploy to production') {
      steps {
        dir(path: 'gameoflife-ansible') {
          sh 'production.yml'
        }
        
      }
    }
  }
}