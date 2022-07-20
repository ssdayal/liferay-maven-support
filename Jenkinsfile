pipeline {
  agent any
  stages {
    stage('build') {
      agent any
      steps {
        sh '''export M2_HOME=/opt/homebrew/Cellar/maven/3.8.6/libexec # your Mavan home path
export PATH=$PATH:$M2_HOME/bin
mvn --version'''
      }
    }

  }
}