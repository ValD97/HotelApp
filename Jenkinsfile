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
        cobertura(coberturaReportFile: '**/target/site/cobertura/coverage.xml')
      }
    }
    stage('SonarQube') {
      steps {
        withSonarQubeEnv('Local Sonarqube') {
          sh 'mvn  sonar:sonar'
        }

      }
    }
  }
}