pipeline {
  agent any
  tools {
    maven 'mvn-3'
    jdk 'jdk7'
  }
  options {
    buildDiscarder(logRotator(numToKeepStr:'3'))
  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package -Pbuild-distr -DskipTests -Pdse-5.0.4'
      }
    }
    stage('Archive') {
      steps {
        archiveArtifacts(artifacts: 'zeppelin-distribution/target/*.tar.gz', fingerprint: true, onlyIfSuccessful: true)
      }
    }
  }
}
