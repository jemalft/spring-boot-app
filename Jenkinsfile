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
    stage('Static Analysis') {
      steps {
        sh './gradlew checkstyleMain checkstyleTest findbugsMain findbugsTest'
      }
    }
    stage('Build') {
      steps {
        sh './gradlew -x test -x check build'
      }
    }
  }
}