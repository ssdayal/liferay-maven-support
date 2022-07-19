pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        build(job: 'mvn clean install', quietPeriod: 5)
      }
    }

  }
}