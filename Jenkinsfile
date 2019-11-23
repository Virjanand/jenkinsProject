pipeline {
  agent { label 'slave01'}
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/Virjanand/jenkinsProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clear compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}