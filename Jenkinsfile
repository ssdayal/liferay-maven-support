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

    stage(' Pre Build') {
      steps {
        sh '''export M2_HOME=/opt/homebrew/Cellar/maven/3.8.6/libexec # your Mavan home path
export PATH=$PATH:$M2_HOME/bin
mvn -Dmaven.test.failure.ignore=true install



'''
      }
    }

    stage('Build') {
      steps {
        sh '''export M2_HOME=/opt/homebrew/Cellar/maven/3.8.6/libexec # your Mavan home path
export PATH=$PATH:$M2_HOME/bin
mvn package -Dmaven.test.skip=true'''
      }
    }

    stage('artifactory') {
      steps {
        archiveArtifacts(artifacts: 'target/*.jar', allowEmptyArchive: true, caseSensitive: true, defaultExcludes: true)
      }
    }

  }
}