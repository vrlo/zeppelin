pipeline {
  agent any
  tools {
    maven 'mvn-3'
    jdk 'jdk8'
  }
  options {
    buildDiscarder(logRotator(numToKeepStr:'3'))
  }
  stages {
    stage('Build') {
      steps {
        sh './dev/change_scala_version.sh 2.11'
        sh 'mvn clean package -Pbuild-distr -DskipTests -Pdse-5.1.0 -Pscala-2.11'
      }
    }
    stage('Archive') {
      steps {
        archiveArtifacts(artifacts: 'zeppelin-distribution/target/*.tar.gz', fingerprint: true, onlyIfSuccessful: true)
      }
    }
  }
}
