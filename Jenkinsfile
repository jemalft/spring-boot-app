pipeline {
  agent any

  stages {
    stage('Clean') {
      steps {
        sh './gradlew clean'
      }
    }
    stage('Compile') {
      steps {
        sh './gradlew compileJava compileTestJava'
      }
    }
    stage('Test') {
      steps {
        sh './gradlew test'
      }
    }
    stage('Build') {
      steps {
        sh './gradlew -x test build'
      }
    }
  }
}