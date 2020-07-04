pipeline {
  agent {
    node {
      label 'master'
    }
  }
  stages {
    stage('Build') {
      steps {
        withMaven(maven: 'M3') {
          bat 'mvn clean install'
        }
      }
    }
    stage('Results') {
      steps {
        junit '**/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }
  }
}
