pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('test') {
      steps {
        sh './mvnw clean test'
      }
    }

    stage('package') {
      steps {
        sh './mvnw install'
      }
    }

  }
}
