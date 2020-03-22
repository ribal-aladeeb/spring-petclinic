pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''./mvnw clean compile'''
      }
    }

    stage('test') {
      steps {
        sh './mvnw clean test'
      }
    }

    stage('package') {
      steps {
        sh './mvnw package'
      }
    }

  }
  post {
    failure {
      sh "git bisect start ${BROKEN} ${STABLE}"
      sh 'git bisect run mvn clean test'
      sh 'git bisect reset'
    }

  }
