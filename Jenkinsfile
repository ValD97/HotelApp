pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test cobertura:cobertura'
      }
    }
    stage('Report') {
      steps {
        sh 'cobertura coberturaReportFile: \'**/target/site/cobertura/coverage.xml\''
      }
    }
  }
}