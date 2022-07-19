pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''apt install default-jdk
wget https://dlcdn.apache.org/maven/maven-3/3.8.4/binaries/apache-maven-3.8.4-bin.tar.gz -P /tmp
tar xf /tmp/apache-maven-*.tar.gz -C /opt
ln -s /opt/apache-maven-3.8.4 /opt/maven
export JAVA_HOME=/usr/lib/jvm/default-java
export M2_HOME=/opt/maven
export MAVEN_HOME=/opt/maven
export PATH=${M2_HOME}/bin:${PATH}
chmod +x /etc/profile.d/maven.sh
source /etc/profile.d/maven.sh'''
        sh 'ls -l'
      }
    }

  }
}