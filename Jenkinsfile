pipeline {
  agent any
  stages {
    stage('build') {
      agent any
      steps {
        sh '''mvn -version
java --version
'''
      }
    }

  }
}