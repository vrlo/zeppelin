pipeline {
  agent any
  tools {
    maven 'mvn-3'
    jdk 'jdk7'
  }
  stages {
    stage('Test tools') {
      steps {
        sh 'javac -version'
      }
      steps {
        sh 'mvn --version'
      }
    }
  }
}
