pipeline {
  agent any
  stages {
    stage('Intial') {
      parallel {
        stage('Intial') {
          agent any
          steps {
            sh '''export M2_HOME=/opt/homebrew/Cellar/maven/3.8.6/libexec # your Mavan home path
export PATH=$PATH:$M2_HOME/bin
mvn --version
java --version
git --version
ls -l'''
          }
        }

        stage('file') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('Build') {
      steps {
        sh '''export M2_HOME=/opt/homebrew/Cellar/maven/3.8.6/libexec # your Mavan home path
export PATH=$PATH:$M2_HOME/bin
mvn package'''
      }
    }

    stage('post-build') {
      steps {
        echo 'The build is completed successfully'
      }
    }

  }
}