pipeline {
  agent any
  stages {
    stage('pre build') {
      parallel {
        stage('pre build') {
          steps {
            sh '''export M2_HOME=/opt/homebrew/Cellar/maven/3.8.6/libexec # your Mavan home path
export PATH=$PATH:$M2_HOME/bin
git --version
java --version
mvn -version'''
          }
        }

        stage('files') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('build') {
      steps {
        sh '''export M2_HOME=/opt/homebrew/Cellar/maven/3.8.6/libexec # your Mavan home path
export PATH=$PATH:$M2_HOME/bin

mvn -Dmaven.test.failure.ignore=true install'''
      }
    }

    stage('test') {
      steps {
        junit '**/surefire-reports/**/*.xml'
      }
    }

    stage('artifact') {
      steps {
        archiveArtifacts 'liferay-maven-support/target/*jar'
      }
    }

  }
}