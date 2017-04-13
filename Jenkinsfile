pipeline {
  agent any
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