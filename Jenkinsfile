pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn clean install -Dlicense.skip=true'
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
      }
    }

  }
}